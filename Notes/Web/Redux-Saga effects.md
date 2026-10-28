# Redux-Saga effects

Map: [[Maps/Web development|Web development]]

## Summary

A saga yields effects describing asynchronous work and coordination. Choose the effect according to the required concurrency and cancellation behavior.

## Effect reference

| Effect/helper | Purpose |
| --- | --- |
| `call` | Invoke an operation and wait for its result. |
| `put` | Dispatch an action. |
| `select` | Read state through a selector. |
| `take` | Wait for a matching action or channel value. |
| `takeEvery` | Start a task for every matching action. |
| `takeLatest` | Start the latest task and cancel the previous running task. |
| `all` | Coordinate several effects together. |
| `race` | Keep the winning outcome and cancel losing effects. |
| `delay` | Wait without blocking the JavaScript thread. |
| `throttle` | Limit how frequently matching work starts. |

Cancellation of saga execution does not automatically undo a remote side effect. The underlying operation needs compatible cancellation behavior.

## Related

- [[Notes/JavaScript/Promises and async await|Promises and async await]]
- [[Notes/JavaScript/Timers debounce and throttle|Timers debounce and throttle]]

## Sources

- [Redux-Saga API](https://redux-saga.js.org/docs/api/)
