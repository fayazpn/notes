# Byzantine faults

Map: [[Maps/Systems|Systems]]

## Summary

A Byzantine participant can behave arbitrarily, including sending conflicting messages to different peers. Consensus protocols define how correct participants can still agree under stated assumptions.

## Key points

- Agreement concerns correct participants choosing compatible outcomes.
- Validity constrains which outcomes may be chosen; the exact condition depends on the protocol.
- Liveness asks whether the system eventually makes progress, under its timing/network assumptions.
- A fault-tolerance bound is meaningful only with its model: authentication, synchrony, membership, and failure assumptions matter.

## Related

- [[Notes/Blockchain/Blockchain basics|Blockchain basics]]
- [[Notes/Systems/Centralization tradeoffs|Centralization tradeoffs]]
