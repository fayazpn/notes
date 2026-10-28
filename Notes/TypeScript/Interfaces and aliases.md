# Interfaces and aliases

Map: [[Maps/TypeScript|TypeScript]]

## Summary

Interfaces name object contracts and can be extended or declaration-merged. Type aliases can name object types, unions, primitives, and other type expressions.

## Key points

- An interface can extend compatible object contracts. A type alias can combine types with intersections.
- A class can implement an interface or a suitable object type alias.
- Repeated compatible interface declarations merge; aliases cannot be reopened this way.
- Both describe compile-time contracts, not runtime validation.

## Example

```ts
interface User { id: number }
interface Admin extends User { role: "admin" }
type ID = string | number;
```

## Related

- [[Notes/TypeScript/Unions and intersections|Unions and intersections]]
- [[Notes/TypeScript/Generics|Generics]]
