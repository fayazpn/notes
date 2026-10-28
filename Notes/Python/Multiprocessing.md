# Multiprocessing

Map: [[Maps/Python|Python]]

## Summary

Running separate processes, each with its own interpreter and memory. This can provide parallel execution for CPU-bound work.

## Key points

- Bypasses the GIL entirely since each process has its own interpreter
- Higher overhead than threads (separate memory, slower startup, pickling to communicate)
- `multiprocessing.Pool` distributes work across CPU cores
- `concurrent.futures.ProcessPoolExecutor` mirrors the thread pool API

## Practice

- [ ] Parallelize a CPU-heavy function (e.g. computing primes) across cores with `Pool.map`
- [ ] Compare wall-clock time of the same task via threading vs multiprocessing
- [ ] Explain why data passed between processes must be picklable

## Related

- [[Notes/Python/Multithreading|Multithreading]]
- [[Notes/Python/Memory Management and the GIL|Memory Management and the GIL]]
