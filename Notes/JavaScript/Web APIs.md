# Web APIs

Map: [[Maps/JavaScript|JavaScript]]

## Summary

The browser supplies DOM, networking, storage, and history APIs around the JavaScript language.

## Key points

- `querySelector` locates a DOM element; `addEventListener` subscribes to events.
- Events may capture toward the target and bubble outward. Event delegation handles descendant events from a parent listener.
- `AbortController` can signal cancellation to supported APIs such as `fetch`; cancellation does not guarantee a remote effect was undone.
- `localStorage` persists origin-scoped strings; `sessionStorage` is scoped to a tab's page session. Do not use them as secret stores.
- `history.pushState` adds an entry; `replaceState` changes the current entry without a full-page navigation.

## Related

- [[Notes/JavaScript/Promises and async await|Promises and async await]]
- [[Notes/Web/Next.js navigation|Next.js navigation]]
