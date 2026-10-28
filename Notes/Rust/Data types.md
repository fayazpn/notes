# Data types

Map: [[Maps/Rust|Rust]]

## Summary

Rust has scalar types, fixed-size aggregates, and collection types. Arrays and vectors both contain elements of one element type.

## Key points

- Integers include signed `i8`–`i128` and unsigned `u8`–`u128`; `isize`/`usize` are pointer-sized.
- Floating-point types are `f32` and `f64`; `bool` stores a boolean and `char` stores a Unicode scalar value.
- Tuples group possibly different types. `[T; N]` is an array; `Vec<T>` is a growable contiguous collection of `T`.
- `&str` is a borrowed string slice; `String` owns a growable UTF-8 string.
- `HashMap<K, V>` maps keys to values; `insert(key, value)` uses ordinary positional arguments.
- Structs name fields; enums represent alternatives, potentially with associated data.

## Example

```rust
let point: (i32, i32) = (2, 3);
let fixed: [i32; 3] = [1, 2, 3];
let mut values: Vec<i32> = vec![1, 2, 3];
values.push(4);
```

## Related

- [[Notes/Rust/Borrowing and mutability|Borrowing and mutability]]

## Sources

- [Rust book: vectors](https://doc.rust-lang.org/book/ch08-01-vectors.html)
