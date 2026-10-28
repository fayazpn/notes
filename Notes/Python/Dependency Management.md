# Dependency Management

Map: [[Maps/Python|Python]]

## Summary

Tracking, pinning, and resolving the external packages a project needs, reproducibly.

## Key points

- `requirements.txt` (pip) vs lockfiles (`poetry.lock`, `uv.lock`) - lockfiles pin exact transitive versions
- Semantic versioning: MAJOR.MINOR.PATCH and what each number implies about compatibility
- Separate dev dependencies (testing, linting) from runtime dependencies
- Dependency conflicts are a top reason virtual environments matter - see [[Notes/Python/Virtual Environments|Virtual Environments]]

## Practice

- [ ] Pin a requirements.txt to exact versions vs loose (>=) versions and explain the tradeoff
- [ ] Separate a project's dependencies into requirements.txt and requirements-dev.txt
- [ ] Explain what a lockfile guarantees that a plain requirements.txt doesn't

## Related

- [[Notes/Python/Virtual Environments|Virtual Environments]]
- [[Notes/Python/Packaging and pyproject.toml|Packaging and pyproject.toml]]
