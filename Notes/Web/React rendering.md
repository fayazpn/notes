# React rendering

Map: [[Maps/Web development|Web development]]

## Summary

Rendering means React calls components to calculate the next UI. A render does not necessarily produce a DOM change.

## Key points

- Initial mounting starts rendering. State updates can render the component and descendants.
- Parent updates can cause child rendering; context consumers also update when the context value they read changes.
- Props participate in that update model. Avoid blanket claims that props either always or never cause rendering.
- Memoization can skip suitable work when inputs are unchanged, but correctness must not depend on a render being skipped.

## Related

- [[Notes/Web/React composition|React composition]]
- [[Notes/Web/React state and effects|React state and effects]]

## Sources

- [React render and commit](https://react.dev/learn/render-and-commit)
