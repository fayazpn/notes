# Valid parentheses

Map: [[Maps/DSA|DSA]]

## Summary

A stack tracks opening brackets that must be closed in reverse order.

## Key points

- Push an opening bracket.
- For a closing bracket, require a nonempty stack with a matching top, then pop it.
- Accept only if the stack is empty at the end. Time O(n), space O(n).

## Example

`"([])"` is valid; `"([)]"` is invalid.

## Related

- [[Notes/DSA/Min stack|Min stack]]
