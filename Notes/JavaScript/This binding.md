# This binding

Map: [[Maps/JavaScript|JavaScript]]

## Summary

For ordinary functions, `this` usually depends on the call form. Arrow functions capture `this` from their enclosing scope.

## Key points

- `object.method()` supplies `object` as the receiver.
- Extracting a method and calling it separately loses that receiver. A plain strict-mode call has `this === undefined`.
- `call`, `apply`, and `bind` set or bind the receiver for an ordinary function.
- `new Constructor()` creates a new instance receiver. Arrow functions do not provide their own `this` and cannot be constructors.

## Example

```js
const user = { name: "Fayaz", read() { return this.name; } };
const read = user.read.bind(user);
read(); // "Fayaz"
```

## Saved diagrams

![[Attachments/JavaScript/ordinary-function-this.png]]

![[Attachments/JavaScript/arrow-function-this.png]]

## Related

- [[Notes/JavaScript/Prototypes classes and new|Prototypes classes and new]]
