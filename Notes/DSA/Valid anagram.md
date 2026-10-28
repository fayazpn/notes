# Valid anagram

Map: [[Maps/DSA|DSA]]

## Summary

Two strings are anagrams when they contain the same character counts.

## Key points

- Reject different lengths first.
- Count characters in the first string, then consume those counts with the second.
- Average time O(n), extra space O(k) for k distinct characters.

## Example

```python
def valid_anagram(first, second):
    if len(first) != len(second):
        return False
    counts = {}
    for char in first:
        counts[char] = counts.get(char, 0) + 1
    for char in second:
        if counts.get(char, 0) == 0:
            return False
        counts[char] -= 1
    return True
```

## Related

- [[Notes/DSA/Group anagrams|Group anagrams]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=9UtInBqnCgA&ab_channel=NeetCode)
