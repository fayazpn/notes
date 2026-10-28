# Scope and LEGB

Map: [[Maps/Python|Python]]

## Summary

The rule Python uses to resolve a variable name: Local, Enclosing, Global, Built-in.

## Key points

- `global` keyword lets a function modify a module-level variable
- `nonlocal` lets a nested function modify an enclosing function's variable - key to [[Notes/Python/Closures|Closures]]
- Each function call creates a new local scope
- Name resolution happens at call time, not definition time (relevant to closure bugs)

## Practice

- [ ] Predict output of a function that shadows a global variable of the same name
- [ ] Fix a closure-in-a-loop bug using `nonlocal` or a default argument
- [ ] Explain LEGB with a 3-level nested function example

## Related

- [[Notes/Python/Closures|Closures]]
- [[Notes/Python/Functions|Functions]]
