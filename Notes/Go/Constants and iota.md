# Constants and iota

Map: [[Maps/Go|Go]]

## Summary

`const` declares compile-time constants. `iota` produces successive integer values inside a constant declaration group.

## Key points

- Constants need a constant expression; a function call generally cannot initialize one.
- A named type can make a related set of constants clearer.
- Reordering an `iota` group changes its numeric values. Use explicit values for stable external protocols when needed.
- A constant group does not prevent a variable of that numeric type from holding other values; validate external input.

## Example

```go
type Day int

const (
    Sunday Day = iota
    Monday
    Tuesday
)
```

## Related

- [[Notes/Go/Core types|Core types]]
- [[Notes/Go/Variables|Variables]]
