# Group anagrams

Map: [[Maps/DSA|DSA]]

## Summary

Group words by a canonical representation of their character counts.

## Key points

- For lowercase English letters, use a 26-element count tuple as the dictionary key.
- Words with the same count tuple belong to the same group. A mutable dictionary/list cannot itself be a hash-map key.
- Average time O(nk) for n words with maximum length k. Stored output and keys require additional space.
- For another alphabet, change the key representation rather than indexing blindly with `ord(char) - ord("a")`.

## Example

```python
def group_anagrams(words):
    groups = {}
    for word in words:
        counts = [0] * 26
        for char in word:
            counts[ord(char) - ord("a")] += 1
        groups.setdefault(tuple(counts), []).append(word)
    return list(groups.values())
```

## Related

- [[Notes/DSA/Valid anagram|Valid anagram]]
- [[Notes/Python/Tuples|Tuples]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=vzdNOK2oB2E&ab_channel=NeetCode)
