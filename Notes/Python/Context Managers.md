# Context Managers

Map: [[Maps/Python|Python]]

## Summary

Objects that define setup/teardown behavior via `__enter__`/`__exit__`, used with the `with` statement.

## Key points

- Guarantees cleanup (closing files, releasing locks) even if an exception occurs
- `contextlib.contextmanager` decorator turns a generator function into a context manager
- Related to [[Notes/Python/Magic Methods|Magic Methods]] (`__enter__`, `__exit__`) and [[Notes/Python/Exception Handling|Exception Handling]]
- Multiple context managers can be combined: `with open(a) as f1, open(b) as f2:`

## Practice

- [ ] Write a custom context manager class that times a code block
- [ ] Rewrite that timer using `@contextlib.contextmanager` and `yield`
- [ ] Use a context manager to guarantee a lock is released

## Related

- [[Notes/Python/Input Output and File Basics|Input Output and File Basics]]
- [[Notes/Python/Exception Handling|Exception Handling]]
- [[Notes/Python/Magic Methods|Magic Methods]]
