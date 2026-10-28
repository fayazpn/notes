# Input Output and File Basics

Map: [[Maps/Python|Python]]

## Summary

Reading user input and reading/writing files using Python's built-in `open()`.

## Key points

- Always use `with open(...) as f:` - a context manager that auto-closes the file (see [[Notes/Python/Context Managers|Context Managers]])
- Modes: `'r'` read, `'w'` write/overwrite, `'a'` append, `'rb'`/`'wb'` binary
- `input()` always returns a string - cast explicitly for numbers
- Reading large files line-by-line avoids loading everything into memory (see [[Notes/Python/Generators|Generators]])

## Practice

- [ ] Read a text file and count the number of lines
- [ ] Write a list of dicts to a file, one JSON line per record
- [ ] Handle a missing file gracefully with try/except

## Related

- [[Notes/Python/Context Managers|Context Managers]]
- [[Notes/Python/Exception Handling|Exception Handling]]
- [[Notes/Python/Generators|Generators]]
