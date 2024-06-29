
2024-06-28 14:56

Status: #child 

Tags: [[db]]

# Nested Writes 

A *nested write* lets us perform multiple operations with a single Prisma Client API.

Example: Creating a user together with post or updating an order together with an invoice. So Prisma Client ensures that all operations succeeds or fails as a whole.
Following example : Create a new user with two posts in a single transaction

```js
const newUser: User = await prisma.user.create({
  data: {
    email: 'alice@prisma.io',
    posts: {
      create: [
        { title: 'Join the Prisma Discord at https://pris.ly/discord' },
        { title: 'Follow @prisma on Twitter' },
      ],
    },
  },
})
```


# Batch/bulk operations

The following bulk operations run as transactions:
- `deleteMany()`
- `updateMany()`
- `createMany()`
- `createManyAndReturn()`

# The $transaction API

**Sequential operations** : Pass an array of Prisma Client queries to be executed sequentially inside of a transaction.
`$transaction<R>(queries: PrismaPromise<R>[]): Promise<R[]>`

**Interactive Transactions** :  Pass a function that can contain user code including Prisma Client queries, non-Prisma code and other control flow to be executed in a transaction.
- **Use interactive transactions with caution**. Keeping transactions open for a long time hurts database performance and can even cause deadlocks. Try to avoid performing network requests and executing slow queries inside your transaction functions. We recommend you get in and out as quick as possible!

`$transaction<R>(fn: (prisma: PrismaClient) => R): R`





# References

Prisma Docs - https://www.prisma.io/docs/orm/prisma-client/queries/transactions
[[DB - Prisma Interactive Transactions Example]]




