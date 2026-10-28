# WebSockets

Map: [[Maps/Systems|Systems]]

## Summary

WebSocket provides a persistent, bidirectional message channel after connection setup. An open socket does not by itself make application state reliable.

## Key points

- Establish the connection, authenticate/subscribe as required, and close or clean up listeners when no longer needed.
- Define what each message contains: a notification to refetch, a complete snapshot, or an incremental update.
- Reconnection needs a resynchronization strategy; messages may have been missed while disconnected.
- Plan ordering, duplicate handling, liveness detection, and backpressure at the application level.
- HTTP connections can also persist; the useful distinction is the communication model rather than “HTTP always closes after one response.”

## Related

- [[Notes/Systems/HTTP HTTPS and transport|HTTP HTTPS and transport]]
- [[Private/CoinRoutes/Order table investigation|Order table investigation]]
