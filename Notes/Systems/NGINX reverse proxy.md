# NGINX reverse proxy

Map: [[Maps/Systems|Systems]]

## Summary

A reverse proxy accepts client requests and forwards selected traffic to an application server. NGINX can also serve static files and terminate TLS.

## Key points

- A `server` block selects a virtual host; a `location` block selects request-path handling.
- `proxy_pass` forwards to an upstream application. `root` and `try_files` serve or locate local files and are different operations.
- WebSocket proxying needs appropriate upgrade headers and connection handling.
- Validate configuration before reloading it. Process supervision, TLS, timeouts, and forwarded-header trust belong to the complete deployment design.

## Example

```nginx
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://127.0.0.1:3000;
    }
}
```

## Related

- [[Notes/Systems/Server provisioning|Server provisioning]]
- [[Notes/Systems/WebSockets|WebSockets]]
