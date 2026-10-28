# Database Access and ORMs

Map: [[Maps/Python|Python]]

## Summary

Interacting with databases from Python, either with raw SQL or an Object-Relational Mapper like SQLAlchemy.

## Key points

- An ORM maps database rows to Python objects, so queries look like Python instead of SQL
- Always use parameterized queries, never string-format user input into SQL (SQL injection risk, see [[Notes/Python/Security Best Practices|Security Best Practices]])
- Connection pooling avoids the overhead of opening a new DB connection per request
- Migrations (e.g. Alembic) version-control schema changes over time

## Practice

- [ ] Define a SQLAlchemy model for a User table and query all users
- [ ] Write the same query using raw SQL with parameterized values
- [ ] Explain in one sentence why f-string SQL queries are dangerous

## Related

- [[Notes/Python/API Design and REST Basics|API Design and REST Basics]]
- [[Notes/Python/Security Best Practices|Security Best Practices]]
