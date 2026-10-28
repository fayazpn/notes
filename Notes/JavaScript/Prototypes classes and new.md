# Prototypes classes and new

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Property lookup can follow an object’s prototype chain. Classes express constructor and prototype-based behavior using dedicated syntax.

## Key points

- `Object.create(proto)` creates an object with the specified prototype; `Object.create(null)` has no ordinary prototype chain.
- For ordinary constructors, `new` creates an object linked to the constructor's `prototype`, invokes the constructor with that receiver, and normally returns the instance.
- Instance methods declared in a class body are shared through its prototype.
- A function's `.prototype` and an object's internal prototype are different concepts. Use `Object.getPrototypeOf()` to inspect the latter.

## Example

```js
class Counter {
  constructor() { this.count = 0; }
  increment() { this.count += 1; }
}
const counter = new Counter();
counter.increment();
```

## Saved diagrams

![[Attachments/JavaScript/new-and-prototype.png]]

![[Attachments/JavaScript/class-and-constructor.png]]

## Related

- [[Notes/JavaScript/This binding|This binding]]
- [[Notes/JavaScript/Objects and properties|Objects and properties]]
