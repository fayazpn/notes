# HTTP HTTPS and transport

Map: [[Maps/Systems|Systems]]

## Summary

HTTP describes request/response semantics. HTTPS protects HTTP traffic using TLS; transport protocols determine how bytes or streams move.

## Key points

- A request contains a method, target, headers, and possibly a body. A response has a status, headers, and possibly a body.
- Status classes: 1xx informational, 2xx success, 3xx redirection, 4xx client-side errors, 5xx server-side errors.
- `Accept` describes acceptable response representations; `Content-Type` describes the representation being sent.
- TLS provides encryption, integrity, and peer authentication. Certificates must match the requested identity, which can be a domain or a supported IP identity.
- HTTP/1.1 supports persistent connections. HTTP/2 multiplexes streams over a connection; it is not simply “multiple requests in one response.”
- TCP provides an ordered reliable byte stream. HTTP/1.1 and HTTP/2 commonly use TCP; HTTP/3 uses QUIC over UDP.

## Related

- [[Notes/Systems/DNS and network protocols|DNS and network protocols]]
- [[Notes/Systems/REST API design|REST API design]]
- [[Notes/Systems/WebSockets|WebSockets]]
