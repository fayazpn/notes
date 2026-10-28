# Performance Profiling

Map: [[Maps/Python|Python]]

## Summary

Measuring where a program actually spends time and memory before optimizing, instead of guessing.

## Key points

- `cProfile` gives function-level timing breakdowns
- `timeit` benchmarks small code snippets accurately
- Premature optimization is a trap - profile first, optimize the actual bottleneck
- Common fixes: better algorithms/data structures, caching (see [[Notes/Python/Functools and Itertools|Functools and Itertools]]), vectorizing with NumPy

## Practice

- [ ] Profile a slow function with cProfile and identify the bottleneck line
- [ ] Use timeit to compare list comprehension vs a for-loop for the same task
- [ ] Optimize a profiled bottleneck and confirm the speedup

## Related

- [[Notes/Python/Functools and Itertools|Functools and Itertools]]
- [[Notes/Python/Multithreading|Multithreading]]
