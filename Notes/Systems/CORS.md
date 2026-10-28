# CORS

Map: [[Maps/Systems|Systems]]

## Summary

Cross-Origin Resource Sharing is a browser-enforced mechanism for controlling which cross-origin responses JavaScript may read.

## Key points

- An origin includes scheme, host, and port. Different origins can require CORS permissions even when both endpoints are reachable.
- Some cross-origin requests require an OPTIONS preflight; not every request is preflighted.
- The server responds with allowed origins, methods, headers, and relevant credential policy.
- CORS is not authentication and does not stop non-browser clients from calling an endpoint.

## Related

- [[Notes/Systems/HTTP HTTPS and transport|HTTP HTTPS and transport]]
- [[Notes/Web/Next.js route handlers|Next.js route handlers]]
