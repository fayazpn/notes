# Go overview

Map: [[Maps/Go|Go]]

## Summary

Go is a statically typed language with garbage collection, packages, and built-in concurrency support.

## Key points

- An executable uses `package main` and a `func main()` entry point. Libraries use other package names.
- A package groups source files; imports are declared in each file that uses them.
- A module groups packages and records dependencies in `go.mod`.
- Build output depends on the target platform and any external runtime dependencies; not every build is fully self-contained.
- Structs group fields; methods attach behavior to a type. Go favors composition rather than class inheritance.

## Related

- [[Notes/Go/Variables|Variables]]
- [[Notes/Go/Core types|Core types]]
- [[Notes/Go/Arrays|Arrays]]
- [[Notes/Go/Slices|Slices]]
- [[Notes/Go/Maps|Maps]]
