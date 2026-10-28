# Type queries

Map: [[Maps/TypeScript|TypeScript]]

## Summary

Type operators derive types from existing declarations instead of duplicating their shapes.

## Key points

- `keyof T` gives the permitted property-key type for `T`.
- In a type position, `typeof value` obtains the static type of a value declaration. Runtime JavaScript `typeof` is a different operation.
- An indexed access type such as `User["id"]` obtains a property's value type; a union of keys obtains a union of property types.

## Example

```ts
const response = { id: 1, name: "Fayaz" };
type Response = typeof response;
type Field = keyof Response;
type ID = Response["id"];
```

## Related

- [[Notes/TypeScript/Utility types|Utility types]]
