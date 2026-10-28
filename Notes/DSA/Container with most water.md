# Container with most water

Map: [[Maps/DSA|DSA]]

## Summary

Maximize the area between two height lines.

## Key points

- Area is `min(height[left], height[right]) * (right - left)`.
- Move the shorter boundary inward; reducing width cannot improve the result unless the limiting height increases.
- Time O(n), extra space O(1).

## Example

Heights `[1, 8, 6, 2, 5, 4, 8, 3, 7]` have maximum area `49`.

## Related

- [[Notes/DSA/Trapping rain water|Trapping rain water]]
