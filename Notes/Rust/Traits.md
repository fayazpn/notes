# Traits

Map: [[Maps/Rust|Rust]]

## Summary

A trait defines behavior that multiple types can implement. Trait bounds let generic code depend on that behavior.

## Key points

- `impl Trait for Type` supplies an implementation for a concrete type.
- An ordinary `impl Type` block defines behavior directly on that type.
- Generic bounds such as `T: Shape` require the operations named by the trait.

## Example

```rust
trait Shape {
    fn area(&self) -> f64;
}

fn print_area<T: Shape>(shape: &T) {
    println!("{}", shape.area());
}
```

## Related

- [[Notes/Rust/Functions and methods|Functions and methods]]
