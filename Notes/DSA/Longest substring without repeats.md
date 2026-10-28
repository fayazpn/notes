# Longest substring without repeats

Map: [[Maps/DSA|DSA]]

## Summary

Maintain a sliding window whose characters are all distinct.

## Key points

- Extend the right boundary one character at a time.
- While that character is already in the window, remove characters from the left. A single `if` is insufficient when several removals are needed.
- Track the largest valid window. Time O(n), space O(k) for the window alphabet.

## Example

For `"abcabcbb"`, the longest length is `3`.

## Related

- [[Notes/DSA/Permutation in a substring|Permutation in a substring]]
