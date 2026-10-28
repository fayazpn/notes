# Variables and Data Types

Map: [[Maps/Python|Python]]

## Summary

Variables are names bound to objects. Objects have types; a name can later be rebound to an object of another type.

## Key points

- Core built-in types: `int`, `float`, `str`, `bool`, `NoneType`
- Everything in Python is an object, even numbers and functions
- Variables are references/labels pointing to objects, not boxes holding values
- `id()` returns an object's identity; whether it represents a memory address is implementation-specific. `type()` returns its type

## Practice

- [ ] Explain the difference between `is` and `==`
- [ ] Predict output: two variables assigned the same small int - do they share identity?
- [ ] Show how reassigning a variable doesn't mutate the original object

## Related

- [[Notes/Python/Operators|Operators]]
- [[Notes/Python/Type Conversion and Casting|Type Conversion and Casting]]
- [[Notes/Python/Strings|Strings]]
