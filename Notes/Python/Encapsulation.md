# Encapsulation

Map: [[Maps/Python|Python]]

## Summary

Bundling data with the methods that operate on it, and restricting direct access to protect internal state.

## Key points

- Python has no true 'private' - convention: `_protected`, `__name_mangled`
- `@property` exposes a method as if it were an attribute - controlled read/write access
- Encapsulation supports invariants (e.g. balance can never go negative)
- Getter/setter pattern via `@property` and `@x.setter`

## Practice

- [ ] Add a `@property` for a `radius` that rejects negative values
- [ ] Explain the difference between `_x` and `__x` naming conventions
- [ ] Build a class where an internal list can't be mutated from outside directly

## Related

- [[Notes/Python/OOP Basics|OOP Basics]]
- [[Notes/Python/Property Decorators|Property Decorators]]
