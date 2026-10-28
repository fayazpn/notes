# CI CD Basics

Map: [[Maps/Python|Python]]

## Summary

Continuous integration validates changes automatically. Continuous delivery keeps releases deployable; continuous deployment releases passing changes automatically.

## Key points

- CI: auto-run tests/linters on every push or pull request
- Delivery may retain a release approval step; deployment automates that final release step
- A basic pipeline: install deps, lint, test, build, deploy
- Secrets (API keys, credentials) are stored in the CI platform's secret manager, never in code

## Practice

- [ ] Write a GitHub Actions YAML file that installs deps and runs pytest on push
- [ ] Add a linting step to that pipeline that fails the build on lint errors
- [ ] Explain the difference between Continuous Integration and Continuous Deployment

## Related

- [[Notes/Python/Testing with Pytest|Testing with Pytest]]
- [[Notes/Python/Code Quality and Linting|Code Quality and Linting]]
- [[Notes/Python/Dockerizing Python Apps|Dockerizing Python Apps]]
