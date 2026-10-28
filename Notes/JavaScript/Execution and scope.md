# Execution and scope

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Within one JavaScript agent, synchronous code runs on a call stack. Lexical scope determines which names a function can access.

## Key points

- Calling a function adds a stack frame; returning removes it. Nested calls use last-in, first-out order.
- A function can access bindings where it was defined, regardless of where it is called.
- Functions are values: they can be stored, passed as callbacks, and returned by other functions.
- The host provides asynchronous facilities. Workers can execute in separate agents; “JavaScript is single-threaded” is not a complete description of the whole browser or runtime.

## Related

- [[Notes/JavaScript/Closures|Closures]]
- [[Notes/JavaScript/Event loop|Event loop]]
- [[Notes/JavaScript/Variables and copying|Variables and copying]]
