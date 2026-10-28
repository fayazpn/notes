# Database keys

Map: [[Maps/Systems|Systems]]

## Summary

A primary key identifies a row. A foreign key constrains a reference to a row in another table, or sometimes the same table.

## Key points

- A primary key is unique and non-null; it can contain more than one column.
- A foreign key refers to columns with an appropriate uniqueness constraint, not necessarily only to a primary key.
- Define the intended update/delete behavior for relationships.
- Constraints enforce integrity independently of application-level checks.

## Related

- [[Notes/Systems/Prisma transactions|Prisma transactions]]
- [[Notes/Python/Database Access and ORMs|Database Access and ORMs]]
