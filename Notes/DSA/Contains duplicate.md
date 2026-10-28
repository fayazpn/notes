# Contains duplicate

Map: [[Maps/DSA|DSA]]

## Summary

Determine whether any value occurs more than once.

## Key points

- Keep a set of values already encountered.
- Return true as soon as the next value is already present; otherwise insert it.
- A set is mutable, but its elements must be hashable. Average time O(n), extra space O(n).

## Example

```python
def contains_duplicate(nums):
    seen = set()
    for value in nums:
        if value in seen:
            return True
        seen.add(value)
    return False
```

## Related

- [[Notes/DSA/Longest consecutive sequence|Longest consecutive sequence]]
- [[Notes/Python/Sets|Sets]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=3OamzN90kPg&ab_channel=NeetCode)
