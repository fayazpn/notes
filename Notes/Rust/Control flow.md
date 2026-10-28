# Control flow

Map: [[Maps/Rust|Rust]]

## Summary

Rust uses `loop`, `while`, and `for` for iteration, and `match` for exhaustive pattern selection.

## Key points

- `loop` repeats until an exit such as `break`; `while` checks a condition before each iteration.
- `for item in collection` iterates over an iterable; `0..3` excludes 3 and `0..=3` includes it.
- `match` must cover every possible value. `_` can cover the remainder when appropriate.

## Example

```rust
for number in 0..3 {
    match number {
        0 => println!("start"),
        _ => println!("continue"),
    }
}
```

## Related

- [[Notes/Rust/Data types|Data types]]
