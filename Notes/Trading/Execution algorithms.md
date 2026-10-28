# Execution algorithms

Map: [[Maps/Trading|Trading]]

## Summary

An execution algorithm controls how an order is worked over time. Its objective, constraints, and benchmark should be stated explicitly.

## Key points

- TWAP spreads execution across a time window; the exact schedule and safeguards depend on implementation.
- POV targets participation in observed market volume, changing activity with volume.
- A price limit, completion target, and available liquidity can conflict; an algorithm name does not guarantee completion or a particular cost.
- Distinguish the execution process from the benchmark used to evaluate it.

## Related

- [[Notes/Trading/Smart order routing|Smart order routing]]
- [[Notes/Trading/Order lifecycle|Order lifecycle]]

## Sources

- [CoinRoutes public execution algorithms](https://coinroutes.com/solutions/asset-managers/)
