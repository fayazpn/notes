# Types values and assertions

Map: [[Maps/TypeScript|TypeScript]]

## Summary

TypeScript checks JavaScript statically. An annotation or assertion affects checking; it does not convert or validate runtime data.

## Key points

- `let value: Date` is an annotation; `const answer = 42` can infer the literal type `42`.
- `as Date` does not turn a string into a Date object. Validate external data and construct the required value.
- `any` bypasses checks; prefer `unknown` when a value must be checked before use.
- Return annotations can document and enforce a function's intended contract.

## Example

```ts
const raw: unknown = "2026-10-28";
if (typeof raw === "string") {
  const date = new Date(raw);
}
```

## Related

- [[Notes/TypeScript/Narrowing and exhaustiveness|Narrowing and exhaustiveness]]

## Sources

- [TypeScript handbook: everyday types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)
