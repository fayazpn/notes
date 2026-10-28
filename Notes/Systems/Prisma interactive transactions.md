# Prisma interactive transactions

Map: [[Maps/Systems|Systems]]

## Summary

An interactive transaction lets application logic run between database operations while they remain in one transaction.

## Key points

- Use the callback's transaction client for the participating queries.
- Throwing from the callback causes the transaction to roll back; a successful callback permits commit.
- Keep the transaction short. Avoid slow external calls while holding database locks.
- For a balance-transfer example, a negative-balance check must be considered together with database isolation, concurrent updates, and numeric representation. The example alone is not a complete payment system.

## Example

```ts
await prisma.$transaction(async tx => {
  const row = await tx.account.update({
    where: { id: senderId },
    data: { balance: { decrement: amount } },
  });
  if (row.balance < 0) throw new Error("Insufficient balance");
  await tx.account.update({
    where: { id: recipientId },
    data: { balance: { increment: amount } },
  });
});
```

## Related

- [[Notes/Systems/Prisma transactions|Prisma transactions]]

## Sources

- [Prisma interactive transactions](https://www.prisma.io/docs/orm/prisma-client/queries/transactions#interactive-transactions)
