# Min stack

Map: [[Maps/DSA|DSA]]

## Summary

Store enough minimum history to answer the current minimum after a pop.

## Key points

- One simple design stores `(value, minimum_so_far)` for every pushed entry.
- Popping also removes the matching minimum history, so repeated minima are handled correctly.
- Push, pop, top, and minimum are O(1), with O(n) storage.

## Example

After pushing `3, 1, 1`, popping once still leaves minimum `1`.

## Related

- [[Notes/DSA/Valid parentheses|Valid parentheses]]
