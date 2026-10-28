# Property Decorators

Map: [[Maps/Python|Python]]

## Summary

`@property` lets a method be accessed like an attribute, enabling computed or validated attributes.

## Key points

- `@property` for the getter, `@x.setter` for the setter, `@x.deleter` for deletion
- Lets you start with plain attributes and add validation later without breaking calling code
- A form of [[Notes/Python/Encapsulation|Encapsulation]]
- Read-only properties: define the getter, skip the setter

## Practice

- [ ] Add a computed `full_name` property from `first_name`/`last_name`
- [ ] Make a property that validates its input and raises `ValueError` on bad data
- [ ] Create a read-only property (no setter defined)

## Related

- [[Notes/Python/Encapsulation|Encapsulation]]
- [[Notes/Python/OOP Basics|OOP Basics]]
- [[Notes/Python/Decorators|Decorators]]
