# Sets

Map: [[Maps/Python|Python]]

## Summary

Unordered collections of unique, hashable elements. Optimized for membership testing and set algebra.

## Key points

- Membership testing (`in`) is O(1) average vs O(n) for lists
- Set operations: union `|`, intersection `&`, difference `-`, symmetric difference `^`
- `frozenset` is the immutable, hashable version
- `set(my_list)` removes duplicates but does not preserve input order; use `dict.fromkeys(my_list)` when order matters

## Practice

- [ ] Remove duplicates from a list while preserving order (without using plain `set()`)
- [ ] Find common elements between two lists using set intersection
- [ ] Explain when you'd choose a set over a list

## Related

- [[Notes/Python/Dictionaries|Dictionaries]]
- [[Notes/Python/Lists|Lists]]
