# Slices

Map: [[Maps/Go|Go]]

## Summary

A slice is a view over an underlying array. It stores a pointer to elements, a length, and a capacity.

## Key points

- Slicing or assigning a slice can share the underlying array; changing an element can be visible through another slice.
- `append` returns an updated slice. It reuses capacity when possible and allocates another array when needed.
- Always keep the returned slice: `items = append(items, value)`.
- Use `make` and `copy` for an independent copy; `copy` copies up to the smaller source/destination length.
- Slices are not comparable with `==`, except against `nil`.

## Example

```go
values := []int{10, 20, 30}
view := values[:2]
view[0] = 99
fmt.Println(values[0]) // 99: shared array

independent := make([]int, len(values))
copy(independent, values)
```

## Related

- [[Notes/Go/Arrays|Arrays]]
- [[Notes/Go/Pointers|Pointers]]
