# Asyncio

Map: [[Maps/Python|Python]]

## Summary

Cooperative concurrency using `async`/`await` and an event loop, commonly for coordinating I/O.

## Key points

- `async def` defines a coroutine function; awaiting an operation can suspend the coroutine so the event loop can run other work
- Useful for coordinating concurrent work, especially I/O. Blocking work on the event-loop thread delays other tasks; offload it when appropriate
- `asyncio.gather()` runs multiple coroutines concurrently
- Powers modern frameworks like FastAPI for high-throughput APIs - see [[Notes/Python/API Design and REST Basics|API Design and REST Basics]]

## Practice

- [ ] Write an async function that fetches multiple URLs concurrently with `asyncio.gather`
- [ ] Explain why calling `time.sleep()` inside a coroutine is a bug, and what to use instead
- [ ] Convert a synchronous function into an async one and explain what changed

## Related

- [[Notes/Python/Multithreading|Multithreading]]
- [[Notes/Python/Generators|Generators]]
- [[Notes/Python/API Design and REST Basics|API Design and REST Basics]]

## Sources

- [Python asyncio documentation](https://docs.python.org/3/library/asyncio.html)
