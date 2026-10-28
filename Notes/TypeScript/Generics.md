# Generics

Map: [[Maps/TypeScript|TypeScript]]

## Summary

Generics preserve relationships between input and output types while allowing a function or structure to work with several concrete types.

## Key points

- A type parameter such as `T` is inferred from use or supplied explicitly.
- A constraint such as `T extends { id: number }` requires a known capability.
- Generics provide compile-time relationships; they do not validate external values at runtime.

## Example

```ts
function first<T>(items: T[]): T | undefined {
  return items[0];
}
```

## Related

- [[Notes/TypeScript/Interfaces and aliases|Interfaces and aliases]]
- [[Notes/TypeScript/Utility types|Utility types]]
