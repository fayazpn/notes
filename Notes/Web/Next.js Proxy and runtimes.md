# Next.js Proxy and runtimes

Map: [[Maps/Web development|Web development]]

## Summary

Request interception and runtime selection are distinct concerns. Next.js version 16 renamed the Middleware file convention to Proxy.

## Key points

- Proxy can redirect, rewrite, or alter headers before request handling completes.
- A matcher limits which paths trigger that interception.
- Proxy defaults to the Node.js runtime in version 16; older notes describing every middleware function as an edge function are outdated.
- An Edge Runtime supports a restricted API environment; deployment location and capabilities depend on the platform. Edge is not a synonym for the full Node.js runtime.

## Related

- [[Notes/Web/Next.js routing and structure|Next.js routing and structure]]
- [[Notes/Web/Next.js navigation|Next.js navigation]]

## Sources

- [Next.js Proxy reference and version history](https://nextjs.org/docs/app/api-reference/file-conventions/proxy)
