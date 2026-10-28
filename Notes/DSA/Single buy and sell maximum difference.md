# Single buy and sell maximum difference

Map: [[Maps/DSA|DSA]]

## Summary

Find the largest later-minus-earlier value in an array using one forward pass.

## Key points

- Track the smallest value seen before the current position.
- Compare the current difference with the best so far, then update the minimum.
- Return zero if the contract permits taking no transaction. Time O(n), extra space O(1).

## Example

For `[7, 1, 5, 3, 6, 4]`, the largest valid difference is `6 - 1 = 5`.
