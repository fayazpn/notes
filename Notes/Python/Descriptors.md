# Descriptors

Map: [[Maps/Python|Python]]

## Summary

Objects that customize attribute access via `__get__`/`__set__`/`__delete__` - the mechanism underlying `@property`.

## Key points

- A descriptor is any object implementing at least one of `__get__`/`__set__`/`__delete__`
- Data descriptors (define `__set__` or `__delete__`) take priority over instance `__dict__`
- Used internally for `@property`, methods, and `@staticmethod`/`@classmethod`
- Reusable validation logic across many attributes without repeating `@property` boilerplate

## Practice

- [ ] Write a descriptor class that validates a positive number on assignment
- [ ] Reuse that descriptor across two different attributes in one class
- [ ] Explain the difference between a data descriptor and a non-data descriptor

## Related

- [[Notes/Python/Property Decorators|Property Decorators]]
- [[Notes/Python/Magic Methods|Magic Methods]]
- [[Notes/Python/Metaclasses|Metaclasses]]
