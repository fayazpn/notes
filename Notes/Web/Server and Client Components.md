# Server and Client Components

Map: [[Maps/Web development|Web development]]

## Summary

Server Components run on the server and can access server-side data. Client Components provide stateful interaction and browser behavior.

## Key points

- `"use client"` marks a client boundary; its imported client-side dependencies become part of that boundary.
- Client Components may still have initial HTML rendered on the server. Put browser-only work in an appropriate client lifecycle or event path.
- Props crossing from server to client must be serializable by React. Ordinary function props cannot simply cross that boundary.
- A Server Component can render a Client Component. Server-rendered content can be passed into a client wrapper through children or other slots.
- Server Components are React components; React still manages their rendering and composition.

## Related

- [[Notes/Web/Next.js data and caching|Next.js data and caching]]
- [[Notes/Web/React state and effects|React state and effects]]

## Sources

- [Next.js Server and Client Components](https://nextjs.org/docs/app/getting-started/server-and-client-components)
