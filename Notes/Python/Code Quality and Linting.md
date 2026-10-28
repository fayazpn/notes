# Code Quality and Linting

Map: [[Maps/Python|Python]]

## Summary

Automated tools that catch style issues, bugs, and type errors before code ships.

## Key points

- `black` - opinionated auto-formatter, ends style debates
- `ruff`/`flake8` - linters catching unused imports, style violations, some bugs
- `mypy` - static type checker, works with [[Notes/Python/Type Hinting|Type Hinting]]
- Pre-commit hooks run these automatically before each git commit

## Practice

- [ ] Run black and ruff on a messy script and review the diffs
- [ ] Set up a pre-commit hook that runs black before every commit
- [ ] Fix 3 lint warnings on a sample file (unused import, line too long, bare except)

## Related

- [[Notes/Python/Type Hinting|Type Hinting]]
- [[Notes/Python/Testing with Pytest|Testing with Pytest]]
- [[Notes/Python/CI CD Basics|CI CD Basics]]
