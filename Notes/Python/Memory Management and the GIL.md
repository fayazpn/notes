# Memory Management and the GIL

Map: [[Maps/Python|Python]]

## Summary

How CPython allocates, reference-counts, and garbage-collects objects, and why the GIL exists.

## Key points

- Reference counting: an object is freed when its refcount hits zero
- Cyclic garbage collector handles reference cycles that refcounting alone can't free
- In a GIL-enabled CPython build, only one thread executes Python bytecode at a time. Optional free-threaded builds have different behavior
- `sys.getrefcount()` and the `gc` module let you inspect this directly

## Practice

- [ ] Use `gc.collect()` and `gc.get_count()` to inspect the garbage collector
- [ ] Create a reference cycle and show the cyclic GC eventually frees it
- [ ] Explain in 2 sentences why the GIL exists and its main tradeoff

## Related

- [[Notes/Python/Multithreading|Multithreading]]
- [[Notes/Python/Multiprocessing|Multiprocessing]]

## Sources

- [Python threading documentation](https://docs.python.org/3/library/threading.html)
