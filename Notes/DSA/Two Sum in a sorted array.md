# Two Sum in a sorted array

Map: [[Maps/DSA|DSA]]

## Summary

Sorted order lets two pointers eliminate impossible pairs without storing a lookup table.

## Key points

- Start at the leftmost and rightmost values.
- If their sum is too small, move left inward; if too large, move right inward.
- The example returns 1-based indices, matching the common exercise contract.
- Time O(n), extra space O(1). Unsorted input does not support this argument.

## Example

```python
def two_sum_sorted(nums, target):
    left, right = 0, len(nums) - 1
    while left < right:
        total = nums[left] + nums[right]
        if total == target:
            return [left + 1, right + 1]
        if total < target:
            left += 1
        else:
            right -= 1
    return []
```

## Related

- [[Notes/DSA/Two Sum|Two Sum]]
- [[Notes/DSA/Three Sum|Three Sum]]
