# JSON encoding and decoding

Map: [[Maps/Go|Go]]

## Summary

JSON encoding turns Go values into JSON; decoding populates Go values from JSON.

## Key points

- `json.Marshal` and `json.Unmarshal` work with byte slices.
- `json.NewEncoder(writer)` and `json.NewDecoder(reader)` work with streams.
- Struct fields must be exported to participate normally. Struct tags control JSON field names.
- Decode into a pointer. Check decoding errors, validate input, and set the response content type before writing.

## Example

```go
type User struct {
    FirstName string `json:"first_name"`
}

var user User
err := json.Unmarshal([]byte(`{"first_name":"Fayaz"}`), &user)
```

## Related

- [[Notes/Go/HTTP handlers|HTTP handlers]]

## Sources

- [Go encoding/json package](https://pkg.go.dev/encoding/json)
