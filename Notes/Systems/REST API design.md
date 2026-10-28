# REST API design

Map: [[Maps/Systems|Systems]]

## Summary

A resource-oriented HTTP API uses a consistent contract for URLs, methods, representations, errors, and authentication.

## Key points

- Use resource names such as `/v1/users/123`, with consistent naming and pagination conventions.
- GET reads; POST commonly creates or triggers processing; PUT replaces a representation; PATCH changes part of it; DELETE removes a resource.
- Statelessness means a request carries the context needed to process it. It does not mean the server has no database, caches, or authentication state.
- Define status codes, validation errors, idempotency behavior, and cache rules explicitly. Not every response should be cached.
- REST is an architectural style; an HTTP endpoint is not automatically RESTful merely because it uses JSON.

## Related

- [[Notes/Systems/HTTP HTTPS and transport|HTTP HTTPS and transport]]
- [[Notes/Python/API Design and REST Basics|API Design and REST Basics]]
- [[Notes/Systems/Graceful shutdown|Graceful shutdown]]
