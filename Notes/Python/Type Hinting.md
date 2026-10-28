# Type Hinting

Map: [[Maps/Python|Python]]

## Summary

Optional static type annotations (`def f(x: int) -> str:`) checked by external tools like mypy, not at runtime.

## Key points

- Doesn't affect runtime behavior by default - it's documentation plus tooling support
- `typing` module: `List`, `Dict`, `Optional`, `Union`, `Callable`, generics
- Python 3.10+ allows `int | None` instead of `Optional[int]`
- Improves IDE autocomplete and catches bugs before running code - essential for production code

## Practice

- [ ] Add type hints to a function with a list argument and dict return type
- [ ] Run `mypy` on a small file and fix a reported type error
- [ ] Explain the difference between `Union[int, str]` and `int | str`

## Related

- [[Notes/Python/Dataclasses|Dataclasses]]
- [[Notes/Python/Code Quality and Linting|Code Quality and Linting]]
