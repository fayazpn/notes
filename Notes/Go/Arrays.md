# Arrays

Map: [[Maps/Go|Go]]

## Summary

An array is a fixed-length sequence of values of one type. The length is part of its type.

## Key points

- `[3]int` and `[4]int` are different types.
- `[...]int{1, 2, 3}` infers the length from the literal at compile time.
- Array assignment and ordinary parameter passing copy the array value.
- Use a slice when a view or a resizable collection is more appropriate.

## Example

```go
values := [3]int{10, 20, 30}
copy := values
copy[0] = 99
fmt.Println(values[0]) // 10
```

## Related

- [[Notes/Go/Slices|Slices]]
