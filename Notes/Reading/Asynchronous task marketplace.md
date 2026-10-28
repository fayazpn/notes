# Asynchronous task marketplace

Map: [[Maps/Life and ideas|Life and ideas]]

## Summary

A course case study connects task submission, object storage, worker responses, and asynchronous payout processing. The reusable lesson is to separate request acceptance from later confirmed outcomes.

## Key points

- A task creator supplies options/assets; workers submit responses against stored task records.
- Store large assets in object storage and store ownership/metadata in the database. Presigned uploads avoid proxying all bytes through the application.
- A submitted payment or payout needs durable state, a stable identifier, and a reconciliation process that checks the actual external result.
- Retrying an uncertain operation must not create a second payout. Define idempotency and reservation/release behavior before implementation.
- Bind any payment proof to the intended task, account, asset, and amount rather than trusting a client-supplied identifier alone.

This is a learning case study, not a verified production design. Key custody, failure recovery, and authorization need their own concrete designs.

## Related

- [[Notes/Systems/S3 presigned URLs|S3 presigned URLs]]
- [[Notes/Systems/Prisma transactions|Prisma transactions]]
- [[Notes/Blockchain/Solana transactions|Solana transactions]]

## Sources

- [Original full-stack course](https://www.youtube.com/watch?v=zi0iR3UN-u0)
