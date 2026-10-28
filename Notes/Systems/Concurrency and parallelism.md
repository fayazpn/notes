# Concurrency and parallelism

Map: [[Maps/Systems|Systems]]

## Summary

Concurrency is organizing multiple tasks whose lifetimes overlap. Parallelism is executing work at the same time.

## Key points

- A single event-loop thread can coordinate concurrent I/O without executing two JavaScript callbacks simultaneously.
- Multiple cores or processes can execute work in parallel.
- Shared mutable state requires a coordination strategy, regardless of how convenient the concurrency API looks.
- Choose a model based on the bottleneck, ordering requirements, and failure behavior, then measure it.

## Related

- [[Notes/Python/Asyncio|Asyncio]]
- [[Notes/Python/Multithreading|Multithreading]]
- [[Notes/Python/Multiprocessing|Multiprocessing]]
- [[Notes/Go/Context cancellation|Context cancellation]]
