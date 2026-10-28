# Dockerizing Python Apps

Map: [[Maps/Python|Python]]

## Summary

Packaging a Python app and its runtime dependencies into a container image.

## Key points

- A Dockerfile defines: base image, copy code, install deps, run command
- Multi-stage builds keep final images small by discarding build-time dependencies
- `.dockerignore` excludes venvs, caches, and secrets from the image
- Pin dependencies and the base image digest when exact rebuild reproducibility is required; image tags can change

## Practice

- [ ] Write a Dockerfile for a simple Flask/FastAPI app
- [ ] Add a .dockerignore file and explain what it prevents
- [ ] Explain the benefit of a multi-stage build in one sentence

## Related

- [[Notes/Python/Dependency Management|Dependency Management]]
- [[Notes/Python/CI CD Basics|CI CD Basics]]
- [[Notes/Python/Config and Environment Variables|Config and Environment Variables]]
