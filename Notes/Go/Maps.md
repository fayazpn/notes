# Maps

Map: [[Maps/Go|Go]]

## Summary

A map stores key-value associations. Keys must be comparable; iteration order is unspecified.

## Key points

- Initialize a map with a literal or `make` before assigning entries.
- Reading an absent key returns the value type's zero value. Use `value, ok := m[key]` to distinguish absence.
- A nil map can be read but assigning an entry to it panics.
- Map values are passed by value, but copies refer to the same map data. Coordinate concurrent access involving writes.

## Example

```go
counts := make(map[string]int)
counts["BTC"]++
count, exists := counts["ETH"]
fmt.Println(count, exists) // 0 false
```

## Related

- [[Notes/Go/Slices|Slices]]
- [[Notes/Go/Pointers|Pointers]]
