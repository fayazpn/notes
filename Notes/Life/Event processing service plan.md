# Event processing service plan

Map: [[Maps/Life and ideas|Life and ideas]]

## Summary

Build a small Go service that accepts work durably and processes it asynchronously, including realistic failure paths.

## Key points

- API: accept and validate commands/events, with a stable request or event identifier.
- Storage: PostgreSQL records durable processing state. State transitions and duplicate handling need explicit rules.
- Worker: process pending work, handle retries, and recover after a worker restart.
- Supporting infrastructure: Redis only where a clear cache/deduplication role is justified; durable correctness should not depend on an unexplained cache entry.
- Observability: logs and metrics expose processing progress, failures, latency, and backlog.
- Failure exercises: duplicate event, retry after an uncertain result, worker restart, and invalid payload.
- Deliverable: a running demonstration and a short design note covering flow, tradeoffs, and failure behavior.

## Related

- [[Notes/Life/Learning priorities|Learning priorities]]
- [[Notes/Systems/Prisma transactions|Prisma transactions]]
- [[Notes/Systems/Graceful shutdown|Graceful shutdown]]
