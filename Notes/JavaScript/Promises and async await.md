# Promises and async await

Map: [[Maps/JavaScript|JavaScript]]

## Summary

A promise represents the eventual outcome of an operation. `async`/`await` provides syntax for composing promise-based work.

## Key points

- A promise is pending, fulfilled, or rejected. Its state and reaction queues are internal, not ordinary public properties.
- `.then()` returns a new promise; returning a value or throwing inside a handler affects that next promise.
- `await` suspends the async function, not the whole event-loop thread. Rejections can be handled with `try`/`catch`.
- `Promise.all()` waits for all inputs to fulfill and rejects if one rejects; it does not cancel the other operations automatically.
- `fetch` does not reject merely because HTTP returned an error status; check `response.ok` when appropriate.

## Example

```js
async function loadUser(url) {
  const response = await fetch(url);
  if (!response.ok) throw new Error(`HTTP ${response.status}`);
  return response.json();
}
```

## Related

- [[Notes/JavaScript/Event loop|Event loop]]
- [[Notes/JavaScript/Web APIs|Web APIs]]

## Sources

- [MDN Promise reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
