# Variables and copying

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Bindings refer to values. Primitive values are copied as values; copying an object reference lets both bindings refer to the same object.

## Key points

- `let` and `const` are block-scoped; `var` is function-scoped. `const` prevents reassignment, not mutation of an object.
- Accessing a `let` or `const` binding before initialization causes a temporal-dead-zone error.
- Assignment and function arguments pass values; an object reference is itself a value.
- Array/object spread creates a shallow copy: nested objects can still be shared.
- Stack-versus-heap placement is an engine implementation detail, not the rule for deciding JavaScript assignment behavior.

## Example

```js
const original = { nested: { count: 1 } };
const copy = { ...original };
copy.nested.count = 2;
console.log(original.nested.count); // 2
```

## Related

- [[Notes/JavaScript/Objects and properties|Objects and properties]]
