# Objects arrays and tuples

Map: [[Maps/TypeScript|TypeScript]]

## Summary

TypeScript describes object shapes, array element types, and positional tuple types. Its object compatibility is primarily structural.

## Key points

- `name?: string` declares an optional property. Fresh object literals receive excess-property checks in relevant assignment contexts.
- `string[]` and `Array<string>` describe arrays of strings.
- `[string, number]` describes a tuple's positions. Use `readonly` when mutation should be rejected by the checker.
- `as const` preserves literal information and produces readonly properties/tuples for the expression; it does not deeply freeze arbitrary runtime objects.

## Example

```ts
type User = { id: number; name?: string };
const point: readonly [number, number] = [2, 3];
```

## Related

- [[Notes/TypeScript/Interfaces and aliases|Interfaces and aliases]]
- [[Notes/TypeScript/Types values and assertions|Types values and assertions]]
