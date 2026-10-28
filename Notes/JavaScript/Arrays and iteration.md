# Arrays and iteration

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Array methods express transformations, searches, and updates. Know whether the method changes the array or returns a new result.

## Key points

- `map` returns mapped values; `filter` returns selected values; `reduce` accumulates a result.
- `find` returns the first matching element, while `some` and `every` return booleans.
- `slice` returns a shallow array copy; `splice` changes the original array. `sort` also changes the original.
- `forEach` returns `undefined`; its callback is useful for side effects. Callbacks to otherwise non-mutating methods can still mutate shared objects.

## Example

```js
const values = [3, 1, 2];
const sorted = [...values].sort((a, b) => a - b);
const doubled = values.map(value => value * 2);
```

## Related

- [[Notes/JavaScript/Variables and copying|Variables and copying]]
