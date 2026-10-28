# Decorators

Map: [[Maps/Python|Python]]

## Summary

A function that takes another function and extends its behavior without modifying it directly. Built on [[Notes/Python/Closures|Closures]].

## Key points

- Syntax sugar: `@my_decorator` above a function def
- Use `functools.wraps` to preserve metadata (`__name__`, docstring)
- Can take arguments (decorator factories — a decorator that returns a decorator)

## Practice

- [x] Write a timing decorator
- [ ] Write a decorator that retries a function N times on failure
- [ ] Write a parameterized decorator (e.g. @repeat(times=3))

## Related

- [[Notes/Python/Functions|Functions]]
- [[Notes/Python/Closures|Closures]]
- [[Notes/Python/Generators|Generators]]
