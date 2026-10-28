# Two Sum

Map: [[Maps/DSA|DSA]]

## Summary

Find two distinct indices whose values sum to the target.

## Key points

- Scan left to right, storing previously seen values and their indices.
- Before storing the current value, look for `target - value`. This avoids reusing the current index.
- Average time O(n), extra space O(n) with a hash map.

## Example

```python
def two_sum(nums, target):
    seen = {}
    for index, value in enumerate(nums):
        other = target - value
        if other in seen:
            return [seen[other], index]
        seen[value] = index
    return []
```

## Related

- [[Notes/DSA/Two Sum in a sorted array|Two Sum in a sorted array]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=KLlXCFG5TnA&ab_channel=NeetCode)
