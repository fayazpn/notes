# OOP Basics

Map: [[Maps/Python|Python]]

## Summary

Classes bundle data (attributes) and behavior (methods). `__init__` sets up instance state; `self` refers to the instance.

## Key points

- Instance vs class attributes
- `@classmethod`, `@staticmethod` — both are examples of [[Notes/Python/Decorators|Decorators]]
- Dunder methods (`__str__`, `__eq__`, `__len__`) let objects work with built-ins

## Practice

- [x] Build a simple `BankAccount` class with deposit/withdraw
- [x] Add `__repr__` and `__eq__` to compare two instances
- [ ] Implement a class with both a `@classmethod` alt-constructor and a `@staticmethod` helper
- [ ] Explain the difference between `self` and `cls`

## Related

- [[Notes/Python/Decorators|Decorators]]
- [[Notes/Python/Inheritance|Inheritance]]
- [[Notes/Python/Magic Methods|Magic Methods]]
