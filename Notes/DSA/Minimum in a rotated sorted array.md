# Minimum in a rotated sorted array

Map: [[Maps/DSA|DSA]]

## Summary

For distinct values, compare the middle value with the rightmost value to find which half contains the minimum.

## Key points

- If `items[middle] > items[right]`, set `left = middle + 1`.
- Otherwise set `right = middle`, keeping the middle as a candidate.
- Stop at `left == right`. Time O(log n) for distinct values; duplicates require extra handling.

## Example

For `[4, 5, 6, 1, 2]`, the minimum is `1` at index `3`.

## Related

- [[Notes/DSA/Binary search|Binary search]]
