# Next.js data and caching

Map: [[Maps/Web development|Web development]]

## Summary

Data fetching, caching, and rendering are separate decisions. Make the freshness requirements explicit rather than assuming every fetch is cached.

## Key points

- An async Server Component can await server-side data without exposing database access to the browser.
- Static/pre-rendered output and request-time rendering have different freshness and request-data requirements.
- Without Cache Components, current `fetch` defaults do not cache requests; `cache: "force-cache"` is an explicit opt-in.
- Revalidation updates selected cached data or paths. It is different from merely re-rendering a component.
- Cache Components and framework-version changes affect the model; check the installed version before copying older settings.

## Related

- [[Notes/Web/Server and Client Components|Server and Client Components]]
- [[Notes/Web/Next.js Server Actions|Next.js Server Actions]]

## Sources

- [Next.js caching without Cache Components](https://nextjs.org/docs/app/guides/caching-without-cache-components)
