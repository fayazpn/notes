# Climbing stairs

Map: [[Maps/DSA|DSA]]

## Summary

If a move climbs one or two steps, ways to reach a step equal the ways to reach the previous two steps added together.

## Key points

- Define a consistent base case: one empty sequence reaches step 0; one sequence reaches step 1.
- For n ≥ 2, `ways[n] = ways[n-1] + ways[n-2]`.
- Store just the previous two values for O(n) time and O(1) auxiliary space.

## Example

Three steps have three sequences: `1+1+1`, `1+2`, and `2+1`.
