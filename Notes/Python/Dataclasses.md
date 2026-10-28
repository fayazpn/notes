# Dataclasses

Map: [[Maps/Python|Python]]

## Summary

The `@dataclass` decorator auto-generates `__init__`, `__repr__`, and `__eq__` for classes that mainly hold data.

## Key points

- Cuts boilerplate vs writing [[Notes/Python/Magic Methods|Magic Methods]] by hand
- `frozen=True` prevents ordinary field reassignment; it does not make nested mutable values immutable - see [[Notes/Python/Tuples|Tuples]]
- Supports default values and `field(default_factory=...)` for mutable defaults
- Type hints are required syntax (though not enforced at runtime) - see [[Notes/Python/Type Hinting|Type Hinting]]

## Practice

- [ ] Convert a hand-written class with `__init__`/`__repr__`/`__eq__` into a `@dataclass`
- [ ] Use `field(default_factory=list)` to safely default a mutable field
- [ ] Create a `frozen=True` dataclass and confirm it raises on mutation

## Related

- [[Notes/Python/OOP Basics|OOP Basics]]
- [[Notes/Python/Tuples|Tuples]]
- [[Notes/Python/Type Hinting|Type Hinting]]
