# Lambda Functions

Map: [[Maps/Python|Python]]

## Summary

Small, anonymous, single-expression functions defined with `lambda args: expression`.

## Key points

- No statements allowed - only a single expression, implicitly returned
- Most common use: a short key function for `sorted()`, `map()`, `filter()`
- Overuse hurts readability - a named function is often clearer
- Cannot have a docstring or type hints

## Practice

- [ ] Sort a list of dicts by a specific key using `sorted(..., key=lambda ...)`
- [ ] Use `map()` with a lambda to square every number in a list
- [ ] Explain when a lambda should be replaced with a regular function

## Related

- [[Notes/Python/Functions|Functions]]
- [[Notes/Python/List Comprehensions|List Comprehensions]]
