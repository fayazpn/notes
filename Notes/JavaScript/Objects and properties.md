# Objects and properties

Map: [[Maps/JavaScript|JavaScript]]

## Summary

Objects associate property keys with values. Property descriptors also control access and enumeration behavior.

## Key points

- `Object.keys`, `Object.values`, and `Object.entries` inspect own enumerable string-keyed properties.
- `{ ...object }` copies own enumerable properties into a new object, but does not deeply clone nested values.
- `Object.defineProperty` controls descriptors such as `writable`, `enumerable`, `configurable`, getters, and setters.
- Copying property descriptors preserves descriptor definitions; it is still not a deep copy.

## Related

- [[Notes/JavaScript/Prototypes classes and new|Prototypes classes and new]]
- [[Notes/JavaScript/Variables and copying|Variables and copying]]
