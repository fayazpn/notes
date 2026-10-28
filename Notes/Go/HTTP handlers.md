# HTTP handlers

Map: [[Maps/Go|Go]]

## Summary

A Go HTTP handler implements `ServeHTTP(http.ResponseWriter, *http.Request)`. `ServeMux` routes requests to handlers.

## Key points

- `http.HandlerFunc` adapts an ordinary function with the handler signature.
- Configure `http.Server` explicitly when you need timeouts and other server settings.
- Write headers and a status before the response body. The first body write sends an implicit success status if none was sent.
- Method-aware patterns such as `GET /hello` require Go 1.22 or later.

## Example

```go
package main

import (
    "log"
    "net/http"
)

func main() {
    mux := http.NewServeMux()
    mux.HandleFunc("GET /hello", func(w http.ResponseWriter, r *http.Request) {
        _, _ = w.Write([]byte("hello"))
    })
    log.Fatal(http.ListenAndServe(":8080", mux))
}
```

## Related

- [[Notes/Go/JSON encoding and decoding|JSON encoding and decoding]]
- [[Notes/Go/Context cancellation|Context cancellation]]

## Sources

- [Go net/http package](https://pkg.go.dev/net/http)
