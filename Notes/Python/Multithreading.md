# Multithreading

Map: [[Maps/Python|Python]]

## Summary

Running multiple threads within one process using `threading`; threads share memory and require coordination.

## Key points

- In GIL-enabled CPython, only one thread executes Python bytecode at a time. Free-threaded builds can run threads in parallel - see [[Notes/Python/Memory Management and the GIL|Memory Management and the GIL]]
- Threads shine for I/O-bound tasks (network calls, file I/O) that release the GIL while waiting
- Race conditions require `threading.Lock` to protect shared state
- `concurrent.futures.ThreadPoolExecutor` provides a higher-level pool API

## Practice

- [ ] Download 5 URLs concurrently using `ThreadPoolExecutor`
- [ ] Demonstrate a race condition on a shared counter, then fix it with a `Lock`
- [ ] Explain why threading doesn't speed up CPU-bound work in CPython

## Related

- [[Notes/Python/Memory Management and the GIL|Memory Management and the GIL]]
- [[Notes/Python/Multiprocessing|Multiprocessing]]
- [[Notes/Python/Asyncio|Asyncio]]

## Sources

- [Python threading documentation](https://docs.python.org/3/library/threading.html)
