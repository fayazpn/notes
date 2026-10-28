# Solana accounts and execution

Map: [[Maps/Blockchain|Blockchain]]

## Summary

Accounts are the fundamental state-storage units on Solana. Programs operate on declared accounts through instructions.

## Key points

- An account has a 32-byte address and fields including a balance, data, and an owner program.
- Program code and application state are modeled through different account roles; the owner controls permitted data modification.
- Instructions declare account access, including read/write requirements. Conflicting writable access constrains scheduling.
- Parallel execution depends on dependencies between transactions; it is not a guarantee that all transactions run in parallel or that other blockchains are inherently single-threaded.

## Related

- [[Notes/Blockchain/Solana transactions|Solana transactions]]
- [[Notes/Systems/Concurrency and parallelism|Concurrency and parallelism]]

## Sources

- [Solana accounts](https://solana.com/docs/core/accounts)
