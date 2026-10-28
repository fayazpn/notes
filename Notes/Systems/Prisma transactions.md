# Prisma transactions

Map: [[Maps/Systems|Systems]]

## Summary

A database transaction groups operations into a unit that commits or rolls back together. Prisma provides several APIs for different dependencies between those operations.

## Key points

- Nested writes create or update related records together.
- Bulk methods such as `createMany` perform a bulk operation atomically as supported by the connector.
- `$transaction([query1, query2])` groups a prepared sequence of Prisma operations.
- An interactive transaction uses a callback for logic between queries.
- Atomicity does not by itself guarantee every concurrency invariant; isolation level, constraints, and retry handling also matter.

## Related

- [[Notes/Systems/Prisma interactive transactions|Prisma interactive transactions]]
- [[Notes/Systems/Database keys|Database keys]]

## Sources

- [Prisma transaction documentation](https://www.prisma.io/docs/orm/prisma-client/queries/transactions)
