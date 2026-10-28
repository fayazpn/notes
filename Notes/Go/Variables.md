# Variables

Map: [[Maps/Go|Go]]

## Summary

Variables have a fixed type. Go can infer the type from an initializer, or use an explicit annotation.

## Key points

- `var` works at package scope and inside functions.
- `:=` is a short declaration used inside functions; it must introduce at least one new variable in the same scope.
- Without an initializer, a variable receives its type's zero value.
- Distinct types such as `int` and `int64` may need an explicit conversion.

## Example

```go
var count int            // 0
var name = "Fayaz"       // inferred string
limit := 10              // inside a function
var seed int64 = 12345
```

## Related

- [[Notes/Go/Core types|Core types]]
- [[Notes/Go/Scope|Scope]]
