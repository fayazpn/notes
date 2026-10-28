# Args and Kwargs

Map: [[Maps/Python|Python]]

## Summary

`*args` collects extra positional arguments into a tuple; `**kwargs` collects extra keyword arguments into a dict.

## Key points

- Order matters: `def f(a, b, *args, c=1, **kwargs)`
- Unpacking works both ways - `f(*my_list, **my_dict)` spreads a collection into arguments
- Used heavily in [[Notes/Python/Decorators|Decorators]] to wrap functions of any signature
- Keyword-only arguments: anything after a bare `*` in the signature

## Practice

- [ ] Write a function that accepts any number of positional and keyword args and prints them
- [ ] Use `*args` unpacking to call `print()` with a list's contents
- [ ] Write a wrapper function using `*args, **kwargs` that forwards to another function

## Related

- [[Notes/Python/Functions|Functions]]
- [[Notes/Python/Decorators|Decorators]]
