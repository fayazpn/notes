# Order lifecycle

Map: [[Maps/Trading|Trading]]

## Summary

Submission, acknowledgement, fills, and cancellation describe different events in an order's lifecycle.

## Key points

- An acknowledgement can report receipt or acceptance according to the protocol; it is not a fill.
- Partial fills change executed and remaining quantities; terminal states must be interpreted using the venue's rules.
- Pending cancel confirms a cancellation request is being processed, not that cancellation is complete. Fills can race with the request.
- Preserve identifiers and event evidence so local state can be reconciled with the venue's reported state.

## Related

- [[Notes/Trading/Smart order routing|Smart order routing]]
- [[Private/CoinRoutes/Order creation investigation|Order creation investigation]]

## Sources

- [FIX order state changes](https://www.fixtrading.org/wp-content/uploads/download-manager-files/FIX-Latest-as-of-EP284-Order-State-Changes.pdf)
