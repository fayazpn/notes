# Event loop

Map: [[Maps/JavaScript|JavaScript]]

## Summary

The event loop coordinates synchronous JavaScript, queued tasks, and microtasks. Asynchronous waiting does not mean the callback executes immediately.

## Key points

- Current synchronous work completes before queued callbacks run on that agent.
- Promise reactions and `queueMicrotask` callbacks use the microtask queue.
- At a microtask checkpoint, queued microtasks are drained before the event loop proceeds to the next task.
- Timers schedule tasks after a minimum delay, not at an exact guaranteed time.
- Long synchronous work or continually queued microtasks can delay input, timers, and rendering. Browser and Node.js scheduling details differ.

## Example

```js
console.log("sync");
setTimeout(() => console.log("timer"), 0);
Promise.resolve().then(() => console.log("promise"));
// sync, promise, timer
```

## Related

- [[Notes/JavaScript/Promises and async await|Promises and async await]]
- [[Notes/JavaScript/Timers debounce and throttle|Timers debounce and throttle]]
