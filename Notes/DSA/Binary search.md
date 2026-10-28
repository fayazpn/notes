# Binary search

Map: [[Maps/DSA|DSA]]

## Summary

Repeatedly eliminate half of a sorted search range using a comparison with its middle element.

## Key points

- For inclusive bounds, start with `left = 0`, `right = len(items) - 1`, and continue while `left <= right`.
- Use the integer midpoint `left + (right - left) // 2`. Update to `middle + 1` or `middle - 1` after excluding it.
- Return the matching index, not a boolean comparison. Time O(log n), space O(1).

## Example

Search for `7` in `[1, 3, 7, 9]` returns index `2`.
