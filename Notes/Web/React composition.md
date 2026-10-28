# React composition

Map: [[Maps/Web development|Web development]]

## Summary

Place state near the components that use it, and compose UI through clear props and children rather than one oversized component.

## Key points

- Moving frequently changing local state into a smaller component can reduce the subtree affected by its updates.
- Passing JSX through `children` lets a wrapper manage its own state without recreating that child element in the wrapper's render function.
- This can avoid unnecessary work, but it is not a guarantee that the child can never render. Its own state, context, and parent inputs still matter.
- Measure before adding memoization solely to chase render counts.

## Saved diagrams

![[Attachments/React/local-state.jpg]]

## Related

- [[Notes/Web/React rendering|React rendering]]
- [[Notes/Web/React state and effects|React state and effects]]

## Sources

- [React props and children](https://react.dev/learn/passing-props-to-a-component)
