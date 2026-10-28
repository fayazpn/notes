# Utility types

Map: [[Maps/TypeScript|TypeScript]]

## Summary

Utility types derive a new contract from an existing one without repeating every property.

## Key points

- `Partial<T>` makes properties optional; `Required<T>` makes them required.
- `Pick<T, K>` selects keys; `Omit<T, K>` removes them.
- `Readonly<T>` prevents assignment to properties through that type; it is not a runtime freeze.
- `Record<K, V>` describes a mapping from keys of type `K` to values of type `V`.

## Example

```ts
type User = { id: number; name: string; email: string };
type PublicUser = Omit<User, "email">;
type UserUpdate = Partial<Pick<User, "name" | "email">>;
```

## Related

- [[Notes/TypeScript/Type queries|Type queries]]
- [[Notes/TypeScript/Generics|Generics]]
