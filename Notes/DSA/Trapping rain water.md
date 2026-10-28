# Trapping rain water

Map: [[Maps/DSA|DSA]]

## Summary

Water at a position is limited by the lower of the highest boundary on either side.

## Key points

- Track left and right maxima while moving the boundary with the lower known maximum inward.
- Add the difference between that boundary maximum and the current height.
- Time O(n), extra space O(1) for the two-pointer approach.

## Example

`[0, 1, 0, 2]` traps one unit above the third position.

## Related

- [[Notes/DSA/Container with most water|Container with most water]]
