# Timers debounce and throttle

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Debouncing waits for a quiet period before acting. Throttling limits how frequently an action can run.

## Key points

- Debounce is useful for reacting after a burst of edits, such as a search query.
- Throttle is useful for rate-limiting frequent events such as scrolling.
- Clear pending timers during cleanup when their callbacks would no longer be valid.

## Example

```js
function debounce(fn, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}
```

## Related

- [[Notes/JavaScript/Closures|Closures]]
- [[Notes/JavaScript/Event loop|Event loop]]
