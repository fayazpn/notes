# Three Sum

Map: [[Maps/DSA|DSA]]

## Summary

Find unique triplets summing to zero by fixing one value and solving a sorted two-pointer problem for the remaining two.

## Key points

1. Sort the values. For each fixed position, skip repeated fixed values.
2. Search the suffix with left/right pointers. Increase the sum by moving left; decrease it by moving right.
3. On a zero sum, record the triplet and skip duplicate pointer values before continuing.
- Time O(n²); extra space depends on the sorting method and the returned results.

## Example

For `[-1, 0, 1, 2, -1, -4]`, the unique value triplets are `[-1, -1, 2]` and `[-1, 0, 1]`.

## Related

- [[Notes/DSA/Two Sum in a sorted array|Two Sum in a sorted array]]
