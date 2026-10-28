# Metaclasses

Map: [[Maps/Python|Python]]

## Summary

Classes of classes - control how classes themselves are created, via `type` or custom metaclasses.

## Key points

- Every class is an instance of `type` by default
- A custom metaclass overrides `__new__`/`__init__` of `type` to change class-creation behavior
- Real-world use: ORMs (Django models), enforcing naming conventions, auto-registering subclasses
- If you're not sure whether you need a metaclass, you probably don't

## Practice

- [ ] Write a metaclass that automatically uppercases all method names in a class
- [ ] Write a metaclass that auto-registers every subclass in a registry dict
- [ ] Explain in one sentence why metaclasses are rarely needed in application code

## Related

- [[Notes/Python/Descriptors|Descriptors]]
- [[Notes/Python/OOP Basics|OOP Basics]]
- [[Notes/Python/Inheritance|Inheritance]]
