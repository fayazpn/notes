# Solana transactions

Map: [[Maps/Blockchain|Blockchain]]

## Summary

A transaction contains one or more instructions, required signatures, and message data such as account references and a recent blockhash.

## Key points

- Instructions identify a program, the relevant accounts, and instruction data.
- Required signatures authorize the message; they do not by themselves prove that execution succeeded.
- Instruction execution is atomic: if an instruction fails, the transaction's instruction state changes revert. Fees may still be charged.
- Submission, confirmation, and expiration are different states. An application needs to check the actual result rather than treating successful RPC submission as execution success.

## Related

- [[Notes/Blockchain/Solana accounts and execution|Solana accounts and execution]]
- [[Notes/Reading/Asynchronous task marketplace|Asynchronous task marketplace]]

## Sources

- [Solana transactions](https://solana.com/docs/core/transactions)
