# Closures

Map: [[Maps/Python|Python]]

## Summary

A function that "remembers" variables from its enclosing scope even after that scope has finished executing.

## Key points

- Requires a nested function and a reference to a variable from the enclosing function
- Basis for [[Notes/Python/Decorators|Decorators]]
- Use `nonlocal` to modify enclosing-scope variables

## Practice

- [x] Write a counter using a closure
- [x] Write an averaging closure that tracks running average
- [ ] Explain why closures can cause late-binding bugs in loops
- [ ] Fix a late-binding bug using default args

## Related

- [[Notes/Python/Functions|Functions]]
- [[Notes/Python/Decorators|Decorators]]
