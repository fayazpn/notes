# Tuples

Map: [[Maps/Python|Python]]

## Summary

Ordered, immutable collections used for fixed groupings of data.

## Key points

- A tuple can be a dictionary key or set element only when every element is hashable
- Tuple unpacking: `a, b = 1, 2` and extended unpacking `a, *rest = [1,2,3]`
- Named tuples (`collections.namedtuple` or `typing.NamedTuple`) add readable field names
- A single-element tuple needs a trailing comma: `(1,)`

## Practice

- [ ] Use tuple unpacking to swap two variables without a temp variable
- [ ] Create a `NamedTuple` for a 2D Point and access fields by name
- [ ] Explain why tuples but not lists can be dict keys

## Related

- [[Notes/Python/Lists|Lists]]
- [[Notes/Python/Dictionaries|Dictionaries]]
- [[Notes/Python/Dataclasses|Dataclasses]]
