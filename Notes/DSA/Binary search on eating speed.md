# Binary search on eating speed

Map: [[Maps/DSA|DSA]]

## Summary

Search an answer range when feasibility is monotonic: a faster eating speed cannot require more total hours.

## Key points

- For positive piles, search speeds from `1` to the largest pile.
- At speed `s`, required hours are the sum of `ceil(pile / s)`. If feasible, search lower speeds; otherwise search higher.
- The standard exercise assumes enough hours to visit every pile. Time O(n log M), where M is the largest pile.

## Example

For piles `[3, 6, 7, 11]` and `8` hours, the minimum speed is `4`.

## Related

- [[Notes/DSA/Binary search|Binary search]]
