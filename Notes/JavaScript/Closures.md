# Closures

Map: [[Maps/JavaScript|JavaScript]]

## Summary

A closure combines a function with access to its surrounding lexical environment. It can retain bindings after the outer call has returned.

## Key points

- The function captures access to bindings, rather than taking a frozen copy of their values.
- Separate calls to a factory function can create independent state.
- Closures support callbacks, function factories, and private state. Retained references can also keep data alive.

## Example

```js
function makeCounter() {
  let count = 0;
  return () => ++count;
}
const counter = makeCounter();
counter(); // 1
counter(); // 2
```

## Related

- [[Notes/JavaScript/Execution and scope|Execution and scope]]
- [[Notes/JavaScript/Timers debounce and throttle|Timers debounce and throttle]]
