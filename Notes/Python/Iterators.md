# Iterators

Map: [[Maps/Python|Python]]

## Summary

An object implementing `__iter__` and `__next__`. Any object you can loop over with `for` is iterable.

## Key points

- `iter(obj)` returns an iterator; `next(it)` advances it
- Raises `StopIteration` when exhausted
- Basis for [[Notes/Python/Generators|Generators]] (generators are a shortcut for writing iterators)

## Practice

- [ ] Write a custom iterator class for a countdown
- [ ] Implement `__iter__`/`__next__` for a linked list
- [ ] Explain the difference between iterable and iterator

## Related

- [[Notes/Python/Generators|Generators]]
- [[Notes/Python/List Comprehensions|List Comprehensions]]
