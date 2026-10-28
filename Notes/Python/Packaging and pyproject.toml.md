# Packaging and pyproject.toml

Map: [[Maps/Python|Python]]

## Summary

Turning a Python project into an installable, distributable package using modern pyproject.toml-based tooling.

## Key points

- `pyproject.toml` can declare build-system requirements and standardized project metadata; older packaging configurations still exist
- Build backends: `setuptools`, `hatchling`, `poetry-core`
- `pip install -e .` (editable install) lets you develop while testing the installed package
- Publishing to PyPI: `python -m build` then `twine upload`

## Practice

- [ ] Write a minimal `pyproject.toml` for a simple package
- [ ] Install your own package in editable mode and import it from another script
- [ ] Explain the difference between setup.py and pyproject.toml-based builds

## Related

- [[Notes/Python/Modules and Packages|Modules and Packages]]
- [[Notes/Python/Virtual Environments|Virtual Environments]]
- [[Notes/Python/Dependency Management|Dependency Management]]
