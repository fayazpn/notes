# Longest consecutive sequence

Map: [[Maps/DSA|DSA]]

## Summary

Find the longest run of consecutive integer values without requiring them to be adjacent in the input.

## Key points

- Put values in a set and iterate over that set, avoiding repeated work from duplicate input values.
- A value starts a sequence only when `value - 1` is absent.
- Count upward from each start. Each distinct value is visited in a sequence at most once.
- Average time O(n), extra space O(n).

## Example

```python
def longest_consecutive(nums):
    values, longest = set(nums), 0
    for value in values:
        if value - 1 not in values:
            length = 1
            while value + length in values:
                length += 1
            longest = max(longest, length)
    return longest
```

## Related

- [[Notes/DSA/Contains duplicate|Contains duplicate]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=P6RZZMu_maU)
