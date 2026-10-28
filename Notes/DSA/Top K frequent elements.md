# Top K frequent elements

Map: [[Maps/DSA|DSA]]

## Summary

Return the k values with the highest occurrence counts.

## Key points

- Count each value, then place values into buckets indexed by frequency.
- Scan buckets from highest frequency down until k values have been collected.
- Average time O(n), extra space O(n). The usual problem contract assumes k does not exceed the number of distinct values.

## Example

```python
def top_k_frequent(nums, k):
    if k <= 0:
        return []
    counts = {}
    for value in nums:
        counts[value] = counts.get(value, 0) + 1
    buckets = [[] for _ in range(len(nums) + 1)]
    for value, count in counts.items():
        buckets[count].append(value)
    result = []
    for count in range(len(nums), 0, -1):
        for value in buckets[count]:
            result.append(value)
            if len(result) == k:
                return result
    return result
```

## Related

- [[Notes/DSA/Group anagrams|Group anagrams]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=YPTqKIgVk-k&ab_channel=NeetCode)
