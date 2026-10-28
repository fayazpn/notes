# Next.js routing and structure

Map: [[Maps/Web development|Web development]]

## Summary

The Next.js App Router organizes routes using folders and special files under `app/`.

## Key points

- `page.tsx` supplies a page at a route segment; folders without pages can organize related files.
- `[id]` is a dynamic segment; `[...slug]` captures multiple segments. Route groups such as `(admin)` organize code without adding that group name to the URL.
- `layout.tsx`, `loading.tsx`, `error.tsx`, and `route.ts` have distinct framework roles.
- Keep shared components, server-only code, hooks, and types in clear project locations without forcing every project into the same large folder tree.
- Check the project's Next.js and Node versions before using setup commands or copying configuration. Old Node 18 and lint presets are not a universal current starter.

## Related

- [[Notes/Web/Next.js layouts and boundaries|Next.js layouts and boundaries]]
- [[Notes/Web/Next.js route handlers|Next.js route handlers]]
- [[Notes/Web/Server and Client Components|Server and Client Components]]
