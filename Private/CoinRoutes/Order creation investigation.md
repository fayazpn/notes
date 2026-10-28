# Order creation investigation

Map: [[Maps/CoinRoutes|CoinRoutes]]

## Summary

Locate the order-creation flow from request entry to response and side effects. These are organized leads from CJ-12599; no repository trace has yet been recorded here.

## First question

Which handler receives the create-order request, and which serializer/create method does it call?

## Search leads to verify

| Area | Question | Lead from the rough note |
| --- | --- | --- |
| Request entry | How are route and serializer connected? | `views/router.py`, serializer `create`, `serializers/__init__.py` |
| Routing | Which CROM implementation handles this request, and how is it selected? | `core/crom.py`, `crom/crom.py`, `crom_managed`, `crom_index` |
| Risk | Which quantities exist before and after adjustment, and what does the frontend consume? | `risk_check`, `exchange_distribution`, `risk_reduced_from_quantity` |
| Persistence | Which write stores the order, and which failures roll it back? | PostgreSQL save path |
| Handoff | Is the CADE boundary IPC, HTTP, or another transport? | CADE, `self.api`, host/port construction using `crom_index` |
| Reservation | What does a PMS reservation reserve, and when is it released? | PMS reservation calls |
| Response | Which result returns to Django, and which events arrive later? | Response/error path and later notifications |

Names above are search leads, not confirmed file locations or a proven call order.

## How to turn this into a code map

1. Record the repository and revision being inspected.
2. Follow one request and record exact file paths, symbols, and callers.
3. Add the state written and a test/log that supports each important step.
4. Trace one failure or cancellation path before describing the flow as understood.

## Questions that remain open

- Does the constructed host/port URL address another process, and which protocol does it use?
- What does `crom_index` identify?
- Is `risk_reduced_from_quantity` the pre-adjustment quantity? Confirm its assignment and every consumer.

## Related

- [[Notes/Trading/Order lifecycle|Order lifecycle]]
- [[Notes/Systems/REST API design|REST API design]]
- [[Notes/Systems/Prisma transactions|Prisma transactions]]
