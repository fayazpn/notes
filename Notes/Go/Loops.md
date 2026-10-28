# Loops

Map: [[Maps/Go|Go]]

## Summary

Go uses `for` for counter loops, condition loops, indefinite loops, and iteration with `range`.

## Key points

- A counter loop has an initializer, a boolean condition, and a post statement.
- `for condition { ... }` repeats while the condition is true; `for { ... }` repeats until control exits.
- `range` iterates over supported values, including slices and maps. Map iteration order is unspecified.
- `_` discards an index or value. Use `break` and `continue` for ordinary loop control.
- `goto` jumps to a label within the same function and has restrictions; use it sparingly.

## Example

```go
for i := 0; i < 3; i++ {
    fmt.Println(i)
}
for key, value := range settings {
    fmt.Println(key, value)
}
```

## Related

- [[Notes/Go/Arrays|Arrays]]
- [[Notes/Go/Slices|Slices]]
- [[Notes/Go/Maps|Maps]]
