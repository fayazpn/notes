# Next.js Server Actions

Map: [[Maps/Web development|Web development]]

## Summary

A Server Action is a server-side function callable through supported mutation flows, including forms and client interactions.

## Key points

- Mark an async server function or a server-only module with `"use server"`; do not define an inline server function inside a Client Component module.
- Read submitted FormData, validate it, and check authentication and authorization on the server.
- Actions can return supported serializable values, including useful results for the calling UI.
- Client state can represent pending, error, and optimistic states. Revalidate relevant data after mutations when needed.
- A server directive is a location boundary, not permission to trust every caller or input.

## Related

- [[Notes/Web/Next.js data and caching|Next.js data and caching]]
- [[Notes/Web/Server and Client Components|Server and Client Components]]

## Sources

- [Next.js mutating data](https://nextjs.org/docs/app/getting-started/mutating-data)
