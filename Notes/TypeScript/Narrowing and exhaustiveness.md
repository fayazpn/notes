# Narrowing and exhaustiveness

Map: [[Maps/TypeScript|TypeScript]]

## Summary

Narrowing reduces the possible types in a control-flow branch. `never` can check that no unhandled union variant remains.

## Key points

- Use `typeof`, `instanceof`, property checks, or a discriminant to narrow a union.
- A user-defined type guard is a promise to the checker; its implementation must actually perform the needed validation.
- `unknown` requires checks before use; `any` suppresses many checks.
- For exhaustive handling, pass the leftover branch to a helper accepting `never`.

## Example

```ts
function assertNever(value: never): never {
  throw new Error(`Unhandled value: ${value}`);
}
```

## Related

- [[Notes/TypeScript/Unions and intersections|Unions and intersections]]
- [[Notes/TypeScript/Types values and assertions|Types values and assertions]]
