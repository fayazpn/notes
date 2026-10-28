# Borrowing and mutability

Map: [[Maps/Rust|Rust]]

## Summary

Borrowing allows access to a value without taking ownership. Shared references permit reading; exclusive mutable references permit mutation.

## Key points

- Bindings are immutable by default; use `let mut` when reassignment or mutation through that binding is needed.
- `&T` is a shared reference; `&mut T` is an exclusive mutable reference.
- For the same data, active shared and mutable borrows cannot conflict.
- A borrow may end after its last use, before the surrounding block ends. The rule is about overlapping live borrows, not simply one entire lexical scope.

## Example

```rust
let mut count = 1;
let value = &mut count;
*value += 1;
println!("{}", count); // mutable borrow is no longer used
```

## Related

- [[Notes/Rust/Data types|Data types]]
- [[Notes/Go/Pointers|Pointers]]

## Sources

- [Rust book: references and borrowing](https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html)
