# Modules and Packages

Map: [[Maps/Python|Python]]

## Summary

Organizing code across files (modules) and folders (packages) for reuse and structure.

## Key points

- A module is any `.py` file; import with `import module` or `from module import x`
- A package is a folder with `__init__.py` (optional since 3.3, but still common)
- `if __name__ == '__main__':` guards code that should only run when the file is executed directly
- Relative vs absolute imports inside a package

## Practice

- [ ] Split a script into two modules and import one from the other
- [ ] Explain what `__name__ == '__main__'` protects against
- [ ] Create a package with two submodules and an `__init__.py`

## Related

- [[Notes/Python/Virtual Environments|Virtual Environments]]
- [[Notes/Python/Packaging and pyproject.toml|Packaging and pyproject.toml]]
