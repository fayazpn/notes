# Polymorphism

Map: [[Maps/Python|Python]]

## Summary

Different classes responding to the same method call in their own way - one interface, many implementations.

## Key points

- Duck typing: Python cares whether an object behaves right, not its declared type
- Achieved via shared method names across unrelated classes, or via [[Notes/Python/Inheritance|Inheritance]] plus method overriding
- Operator overloading (`__add__`, `__eq__`) is a form of polymorphism - see [[Notes/Python/Magic Methods|Magic Methods]]
- Contrast with statically-typed languages' interface-based polymorphism

## Practice

- [ ] Write two unrelated classes that both implement a `.speak()` method and call it polymorphically
- [ ] Overload the `+` operator for a custom Vector class
- [ ] Explain duck typing with a one-sentence example

## Related

- [[Notes/Python/Inheritance|Inheritance]]
- [[Notes/Python/Magic Methods|Magic Methods]]
- [[Notes/Python/OOP Basics|OOP Basics]]
