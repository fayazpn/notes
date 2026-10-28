# Functools and Itertools

Map: [[Maps/Python|Python]]

## Summary

Standard library modules for functional-style programming: composing, caching, and iterating efficiently.

## Key points

- `functools.lru_cache` - automatic memoization decorator
- `functools.reduce` - fold a sequence into a single value
- `functools.partial` - pre-fill some arguments of a function
- `itertools.chain`, `.product`, `.groupby`, `.islice` - memory-efficient iteration tools

## Practice

- [ ] Memoize a slow recursive Fibonacci function with `@lru_cache`
- [ ] Use `itertools.groupby` to group a sorted list of dicts by a field
- [ ] Use `functools.partial` to create a specialized version of a general function

## Related

- [[Notes/Python/Decorators|Decorators]]
- [[Notes/Python/Generators|Generators]]
- [[Notes/Python/Iterators|Iterators]]
