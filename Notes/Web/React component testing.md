# React component testing

Map: [[Maps/Web development|Web development]]

## Summary

Test the behavior visible to a user or consumer of the component. Tests should remain useful when internal implementation details change.

## Key points

- Cover meaningful rendering states, interactions, and callback contracts, rather than every internal function.
- For a reorder UI, perform the interaction and assert the emitted order or visible result.
- Test reducer rules separately when they contain meaningful logic; use integration tests to cover how components and the store work together.
- Keep tests deterministic. Mock external boundaries deliberately, rather than mocking away the behavior being tested.
- Use a small number of valuable cases; repeated assertions about a library's own internals add maintenance cost.

## Related

- [[Notes/Web/React composition|React composition]]
- [[Notes/Python/Testing with Pytest|Testing with Pytest]]
