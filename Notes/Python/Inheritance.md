# Inheritance

Map: [[Maps/Python|Python]]

## Summary

A class can inherit attributes and methods from a parent class, enabling code reuse and polymorphism.

## Key points

- `class Dog(Animal):` — Dog inherits from Animal
- `super().__init__()` delegates to the next initializer in the method resolution order, supporting cooperative inheritance
- Method Resolution Order (MRO) matters with multiple inheritance
- Related to [[Notes/Python/OOP Basics|OOP Basics]]

## Practice

- [ ] Build a 2-level class hierarchy (Animal → Dog → Puppy)
- [ ] Override a parent method and still call the parent version with `super()`
- [ ] Explain MRO with a diamond inheritance example

## Related

- [[Notes/Python/OOP Basics|OOP Basics]]
- [[Notes/Python/Magic Methods|Magic Methods]]
