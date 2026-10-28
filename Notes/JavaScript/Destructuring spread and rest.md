# Destructuring spread and rest

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Destructuring extracts values from a structure. Spread expands values; rest collects the remaining values.

## Key points

- Destructuring defaults apply when the extracted value is `undefined`.
- Rest parameters collect trailing function arguments into an array.
- Object and array spread perform shallow copying or expansion, not deep cloning.

## Example

```js
const [first, ...rest] = [1, 2, 3];
const { name, age = 30 } = { name: "Fayaz" };
const values = [...rest, 4];
```

## Related

- [[Notes/JavaScript/Arrays and iteration|Arrays and iteration]]
- [[Notes/JavaScript/Objects and properties|Objects and properties]]
