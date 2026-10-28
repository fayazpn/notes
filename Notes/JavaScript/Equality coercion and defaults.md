# Equality coercion and defaults

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Strict equality avoids type coercion. Loose equality uses conversion rules that can produce surprising comparisons.

## Key points

- `5 === "5"` is false; `5 == "5"` is true. Prefer strict comparisons unless a specific coercion is intentional.
- Objects compare by identity, not by the equality of their properties.
- Falsy values include `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`, and `NaN`. Empty arrays and objects are truthy.
- `&&` and `||` return operands. `??` falls back only for `null` or `undefined`, preserving values such as `0` and `""`.
- Numeric validation should explicitly convert input and reject unwanted empty strings, `NaN`, or non-integers.

## Example

```js
0 || 10;  // 10
0 ?? 10;  // 0
[] === []; // false: different objects
```

## Related

- [[Notes/JavaScript/Variables and copying|Variables and copying]]
