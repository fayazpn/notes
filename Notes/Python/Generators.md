# Generators

Map: [[Maps/Python|Python]]

## Summary

Functions that use `yield` instead of `return` to produce a lazy sequence of values, pausing state between calls. A simpler way to build [[Notes/Python/Iterators|Iterators]].

## Key points

- `yield` pauses execution and preserves local state
- Memory-efficient for large or infinite sequences
- Generator expressions: `(x*x for x in range(10))`

## Practice

- [ ] Write a generator for the Fibonacci sequence
- [ ] Write a generator that lazily reads a large file line by line
- [ ] Convert a list comprehension into a generator expression and explain the memory difference

## Related

- [[Notes/Python/Iterators|Iterators]]
- [[Notes/Python/Decorators|Decorators]]
- [[Notes/Python/List Comprehensions|List Comprehensions]]
