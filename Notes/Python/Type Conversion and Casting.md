# Type Conversion and Casting

Map: [[Maps/Python|Python]]

## Summary

Converting values between types explicitly (casting) or implicitly (coercion).

## Key points

- Explicit casting: `int('5')`, `str(5)`, `float('3.14')`, `list('abc')`
- Implicit coercion happens in mixed arithmetic: `1 + 2.0` becomes `3.0`
- `int('abc')` raises `ValueError` - always validate or catch when casting user input
- `bool()` on any object uses truthiness rules

## Practice

- [ ] Safely cast user input to int, handling invalid input with try/except
- [ ] Predict the type and value of `int(3.9)` vs `round(3.9)`
- [ ] Convert a list of number-strings into a list of floats

## Related

- [[Notes/Python/Variables and Data Types|Variables and Data Types]]
- [[Notes/Python/Exception Handling|Exception Handling]]
