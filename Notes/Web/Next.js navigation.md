# Next.js navigation

Map: [[Maps/Web development|Web development]]

## Summary

Use a link for ordinary navigation, a router API for client event-driven navigation, and redirect logic where the server determines the destination.

## Key points

- `next/link` supports framework navigation and prefetch behavior.
- App Router client code uses `useRouter` and `usePathname` from `next/navigation`.
- `redirect()` ends the current flow by throwing a framework-managed signal; do not accidentally swallow it in a broad `try`/`catch`.
- `router.push` adds history; `replace` avoids adding another entry. Choose scroll and history behavior deliberately.
- Native `history.pushState` and `replaceState` update the current page's URL/history without a full-page reload.

## Related

- [[Notes/JavaScript/Web APIs|Web APIs]]
- [[Notes/Web/Next.js routing and structure|Next.js routing and structure]]
