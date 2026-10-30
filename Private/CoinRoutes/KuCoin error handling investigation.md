# KuCoin error handling investigation

Map: [[Maps/CoinRoutes|CoinRoutes]]

Started: 2026-10-29
Inspected: repository revision not recorded yet.

> [!note] Working investigation
> Organized from [[Inbox/Capture|Capture]]. The reported behavior and working explanations below still need source paths, logs, or tests. Keep adding KuCoin follow-ups here as the investigation develops.

## Question

How should the KuCoin line handle authentication failures, retries, and spot/futures topics while keeping CROG IPC responsive and unexpected errors visible?

## Observed flow

**First trace:** follow `line_task_main` into the `bullet-private` request and its failure/retry path. Record the actual call order, where the request is awaited, and where cooldown state is checked.

fuc account_info -> appends a product_type_fees from the state or marks it none (ireelevat here) -> waits for *fee_tier_resp* -> everything is ultimatly put in AccouintInfo (class?) -> Traceed the AccountInfo, it is in state.py it is just initialized, I dont see it used

- If we just fix the logger.warning place, the current AttributeError becomes UnboundError (classic python trap of accessing the unassigned value, unlike js there is no undefind state) we need to make the feet_tier assignment safe


![[KuCoin error handling investigation 2026-10-29 15.41.56.excalidraw]]

## Evidence

- Repository and revision: to record.
- Source paths and symbols: locate `KucoinWebsocketLine`, `account_info()`, `self.warning(...)`, `line_task_main`, `account_balance`, and `get_fee_rates`; add file paths and line references.
- Logs and tests: attach examples of error `400003`, the `AttributeError`, retry timing, and futures topics logged by the spot line.

## State and failures

These are observations reported in Capture, pending verification:

| Area                       | Reported behavior                                                                                                                                                                                  | What to check in code or logs                                                                        |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Account information        | `account_info()` fails at `/user-info`, then calls `self.warning(...)`. `KucoinWebsocketLine` has no `warning` attribute; the account-info task raises ==🔴**AttributeError**== every 300 seconds. | Which failure invokes `self.warning`, where logging belongs, and how the task handles the exception. |
| Authentication and retries | Error `400003` is described in the rough notes as ==🔴API Key/site mismatch==. No cooldown was noted in the spot handler; `line_task_main` retries `bullet-private` every 5 seconds.               | Confirm the error meaning, retry interval, and current cooldown behavior.                            |
| Other polling              | `account_balance` runs every 60 seconds and `get_fee_rates` every 30 seconds; both also fail with `400003`.                                                                                        | Whether these calls share authentication/cooldown state or retry independently.                      |
| Topic routing              | The same KuCoin UID trades futures; the spot line receives futures topics and logs them as unhandled.                                                                                              | Which subscriptions/messages reach the spot line and how topics are classified.                      |

## Open questions

- #question What is the missing `warning` attribute supposed to be, and which logging method should this path use?
- #question What does `bullet-private` return? Is the WebSocket server URL always random, or can it vary for another reason?
  - Working understanding from reading: it is a REST endpoint returning a short-lived token and a WebSocket server URL. Verify against the request/response and its caller.
- #question What does “log spam + pool churn” mean for this failure?
  - Rough explanation so far: failed requests repeat, producing repeated logs and repeatedly creating or reusing connections. Check what actually happens to the connection pool before calling it churn.
- #question Why should CROG IPC stay responsive during cooldown, and what does “Never sleep inside a request path awaited by the IPC loop” mean here?
  - Working explanation: one CROG creates and serves many lines. One line with an unusable key should not hold up the process or other healthy lines. Trace the awaits to check how that applies here.
  - Compare blocking sleep with a nonblocking cooldown, including whether the IPC loop still waits for the request path to return.
- #question What does “no traceback” mean for expected failures versus programming errors?
  - Reading takeaway to check against the current handlers: handle failures you expect, keep unexpected bugs visible, and avoid wrapping everything in a blanket `try/except`. Unhandled exceptions can produce tracebacks; decide what each failure should log.
- #question What are spot and futures topics, and which ones should this line handle?
  - Working understanding: topics are like channel names in a WebSocket connection. Verify the actual topic names, subscriptions, and dispatch rules.

## Related

- [[Notes/Systems/WebSockets|WebSockets]]
- [[Notes/Python/Asyncio|Asyncio]]
- [[Notes/Python/Exception Handling|Exception handling]]
