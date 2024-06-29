
2024-06-28 15:22

Status: #child 

Tags:  [[db]]

# DB - Prisma Interactive Transactions


### Use Case 

Let's look at an example:

Imagine that you are building an online banking system. One of the actions to perform is to send money from one person to another.

As experienced developers, we want to make sure that during the transfer,

- the amount doesn't disappear
- the amount isn't doubled

This is a great use-case for interactive transactions because we need to perform logic in-between the writes to check the balance.

In the example below, Alice and Bob each have $100 in their account. If they try to send more money than they have, the transfer is rejected.

Alice is expected to be able to make 1 transfer for $100 while the other transfer would be rejected. This would result in Alice having $0 and Bob having $200.

```js
import { PrismaClient } from '@prisma/client'
const prisma = new PrismaClient()

function transfer(from: string, to: string, amount: number) {
  return prisma.$transaction(async (tx) => {
    // 1. Decrement amount from the sender.
    const sender = await tx.account.update({
      data: {
        balance: {
          decrement: amount,
        },
      },
      where: {
        email: from,
      },
    })

    // 2. Verify that the sender's balance didn't go below zero.
    if (sender.balance < 0) {
      throw new Error(`${from} doesn't have enough to send ${amount}`)
    }

    // 3. Increment the recipient's balance by amount
    const recipient = await tx.account.update({
      data: {
        balance: {
          increment: amount,
        },
      },
      where: {
        email: to,
      },
    })

    return recipient
  })
}

async function main() {
  // This transfer is successful
  await transfer('alice@prisma.io', 'bob@prisma.io', 100)
  // This transfer fails because Alice doesn't have enough funds in her account
  await transfer('alice@prisma.io', 'bob@prisma.io', 100)
}

main()
```

In the example above, both `update` queries run within a database transaction. When the application reaches the end of the function, the transaction is **committed** to the database.

If your application encounters an error along the way, the async function will throw an exception and automatically **rollback** the transaction.

To catch the exception, you can wrap `$transaction` in a try-catch block:


# References

Prisma Docs - https://www.prisma.io/docs/orm/prisma-client/queries/transactions




