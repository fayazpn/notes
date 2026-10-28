# Exception Handling

Map: [[Maps/Python|Python]]

## Summary

Gracefully handling runtime errors with `try`/`except`/`else`/`finally` instead of crashing.

## Key points

- Catch specific exceptions, not bare `except:` (hides bugs)
- `finally` always runs - used for cleanup
- Custom exceptions: subclass `Exception` for domain-specific errors
- `raise ... from e` preserves the original traceback context

## Practice

- [ ] Write a function that retries on a specific exception up to N times
- [ ] Create a custom `InsufficientFundsError` exception class
- [ ] Explain the difference between `except Exception` and bare `except:`

## Related

- [[Notes/Python/Input Output and File Basics|Input Output and File Basics]]
- [[Notes/Python/Context Managers|Context Managers]]
- [[Notes/Python/Logging|Logging]]
