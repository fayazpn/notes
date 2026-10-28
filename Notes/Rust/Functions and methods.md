# Functions and methods

Map: [[Maps/Rust|Rust]]

## Summary

Functions define reusable behavior; an `impl` block attaches associated functions and methods to a type.

## Key points

- Function parameters have explicit types; `-> T` declares a return type.
- The final expression without a semicolon can be returned implicitly.
- `&self` borrows an instance; `&mut self` allows mutation; `self` takes ownership of the receiver.

## Example

```rust
struct Circle { radius: f64 }

impl Circle {
    fn area(&self) -> f64 {
        std::f64::consts::PI * self.radius * self.radius
    }
}
```

## Related

- [[Notes/Rust/Traits|Traits]]
- [[Notes/Rust/Borrowing and mutability|Borrowing and mutability]]
