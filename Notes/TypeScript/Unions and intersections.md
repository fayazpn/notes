# Unions and intersections

Map: [[Maps/TypeScript|TypeScript]]

## Summary

A union `A | B` accepts values from either type. An intersection `A & B` requires compatibility with both.

## Key points

- A union permits only operations valid for the remaining possibilities; narrow it before using variant-specific properties.
- A discriminant such as `kind` connects a literal value with the rest of a variant's shape.
- Incompatible requirements in an intersection can make a value impossible to construct.

## Example

```ts
type Result =
  | { kind: "ok"; value: number }
  | { kind: "error"; message: string };
```

## Related

- [[Notes/TypeScript/Narrowing and exhaustiveness|Narrowing and exhaustiveness]]
- [[Notes/TypeScript/Interfaces and aliases|Interfaces and aliases]]
