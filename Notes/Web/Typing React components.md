# Typing React components

Map: [[Maps/Web development|Web development]]

## Summary

Type props and state so a component's public inputs and event contracts are clear.

## Key points

- A props type can describe required values, optional callbacks, and literal variants.
- Use explicit state types when the initializer does not express every permitted value, such as a nullable selected item.
- A ref's type should match the referenced element or value and account for its initial empty state.
- Type annotations do not replace validation of data arriving from the network.

## Example

```tsx
type ButtonProps = {
  label: string;
  onClick?: () => void;
};

function Button({ label, onClick }: ButtonProps) {
  return <button onClick={onClick}>{label}</button>;
}
```

## Related

- [[Notes/TypeScript/Interfaces and aliases|Interfaces and aliases]]
- [[Notes/TypeScript/Types values and assertions|Types values and assertions]]
