# Core types

Map: [[Maps/Go|Go]]

## Summary

Go provides booleans, numeric types, strings, and reference-like types with defined zero values.

## Key points

- `bool` has `true` and `false`; its zero value is `false`.
- Signed integers are `int8` through `int64`; unsigned integers are `uint8` through `uint64`. `int` and `uint` are platform-sized.
- `byte` aliases `uint8`; `rune` aliases `int32` and commonly represents a Unicode code point.
- `float32` and `float64` represent floating-point numbers. Their zero value is `0`.
- A string is an immutable byte sequence, conventionally UTF-8. Indexing returns a byte; ranging over it decodes runes.
- The zero string is `""`; pointers, slices, maps, channels, functions, and interfaces have `nil` zero values. Reading a nil map or ranging over a nil slice is valid; dereferencing a nil pointer is not.

## Related

- [[Notes/Go/Variables|Variables]]
- [[Notes/Go/Pointers|Pointers]]

## Sources

- [Go specification: types and values](https://go.dev/ref/spec#Types)
