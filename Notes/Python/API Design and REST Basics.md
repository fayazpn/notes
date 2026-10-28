# API Design and REST Basics

Map: [[Maps/Python|Python]]

## Summary

Designing HTTP APIs that are predictable, versioned, and easy to consume, typically with Flask or FastAPI.

## Key points

- REST principles: resources as URLs (/users/1), HTTP verbs (GET/POST/PUT/DELETE) as actions
- Status codes matter: 200 OK, 201 Created, 400 Bad Request, 404 Not Found, 500 Server Error
- FastAPI auto-generates docs and validates request/response bodies from type hints - see [[Notes/Python/Type Hinting|Type Hinting]]
- Versioning (/v1/...) can separate incompatible contracts; compatibility still requires deliberate design and testing

## Practice

- [ ] Build a simple FastAPI endpoint that returns a list of items with proper status codes
- [ ] Add request validation using a Pydantic model
- [ ] Explain why breaking API changes should go into a new version, not overwrite /v1

## Related

- [[Notes/Python/Asyncio|Asyncio]]
- [[Notes/Python/Type Hinting|Type Hinting]]
- [[Notes/Python/Database Access and ORMs|Database Access and ORMs]]
