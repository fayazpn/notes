# Magic Methods

Map: [[Maps/Python|Python]]

## Summary

Dunder ("double underscore") methods let custom objects hook into Python's built-in syntax and functions.

## Key points

- `__str__` / `__repr__` — string representation
- `__eq__`, `__lt__` — comparisons (needed for sorting custom objects)
- `__len__`, `__getitem__`, `__iter__` — make an object behave like a container/[[Notes/Python/Iterators|Iterators]]

## Practice

- [ ] Add `__len__` and `__getitem__` to a custom class so it supports indexing
- [ ] Make two custom objects sortable with `__lt__`
- [ ] Implement `__enter__`/`__exit__` for a custom context manager

## Related

- [[Notes/Python/OOP Basics|OOP Basics]]
- [[Notes/Python/Inheritance|Inheritance]]
- [[Notes/Python/Iterators|Iterators]]
