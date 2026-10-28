# Rust overview

Map: [[Maps/Rust|Rust]]

## Summary

Rust uses ownership and borrowing to manage memory and check many invalid accesses and data races at compile time.

## Key points

- Cargo manages packages, dependencies, builds, and common development tasks.
- `Cargo.toml` declares package metadata and dependencies; `src/main.rs` is the usual executable entry point.
- Ownership checks do not prevent every kind of bug, deadlock, or logical race.
- Safe Rust's guarantees depend on unsafe code and external interfaces upholding their contracts.

## Related

- [[Notes/Rust/Data types|Data types]]
- [[Notes/Rust/Borrowing and mutability|Borrowing and mutability]]
- [[Notes/Rust/Functions and methods|Functions and methods]]
