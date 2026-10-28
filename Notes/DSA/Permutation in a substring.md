# Permutation in a substring

Map: [[Maps/DSA|DSA]]

## Summary

A permutation matches when a fixed-size window has the same character counts as the target.

## Key points

- Count the target and initialize a window of the same length.
- Slide by removing the outgoing character and adding the incoming character.
- Compare counts or maintain a correct mismatch count. With a fixed alphabet, time is O(n), space O(1) relative to string length.

## Example

`"eidbaooo"` contains a permutation of `"ab"`: `"ba"`.

## Related

- [[Notes/DSA/Longest substring without repeats|Longest substring without repeats]]
