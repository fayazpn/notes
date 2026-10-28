# Modules and errors

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Modules define explicit imports and exports. Error handling makes failure paths visible to callers.

## Key points

- Named exports are imported using their exported names; a default export can use a local name chosen by the importer.
- `try`/`catch` handles thrown errors from that execution path. Await asynchronous work inside the `try` when handling its rejection there.
- Throw `Error` objects with useful context. Do not swallow a failure unless recovery is deliberate.
- `finally` handles cleanup when control leaves the `try`/`catch`; process termination can still prevent cleanup.

## Example

```js
// math.js
export const double = value => value * 2;

// consumer.js
import { double } from "./math.js";
```

## Related

- [[Notes/JavaScript/Promises and async await|Promises and async await]]
