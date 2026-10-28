# Abstract Base Classes

Map: [[Maps/Python|Python]]

## Summary

Abstract base classes express interfaces through the `abc` module. A class with unresolved abstract methods cannot be instantiated.

## Key points

- `from abc import ABC, abstractmethod`
- Subclasses MUST implement all `@abstractmethod`s or they can't be instantiated
- Used to define contracts/interfaces in a duck-typed language
- Common in plugin systems and frameworks (e.g. every Shape must implement `.area()`)

## Practice

- [ ] Define an abstract `Shape` class with an abstract `.area()` method
- [ ] Implement `Circle` and `Square` subclasses and confirm instantiating `Shape` directly fails
- [ ] Explain the benefit of ABCs over just trusting subclasses to implement a method

## Related

- [[Notes/Python/Inheritance|Inheritance]]
- [[Notes/Python/Polymorphism|Polymorphism]]
- [[Notes/Python/OOP Basics|OOP Basics]]
