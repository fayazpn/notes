# Proof of History

Map: [[Maps/Blockchain|Blockchain]]

## Summary

In Solana's original design, Proof of History uses a sequential hash sequence to provide verifiable ordering and a notion of elapsed time.

## Key points

- Each hash depends on the previous output; recorded events can be incorporated into that sequence.
- This is a timing/ordering mechanism used alongside consensus, not a complete consensus algorithm on its own.
- Treat this as the original PoH-based design. Upgrades such as Alpenglow change consensus and block-production assumptions; this note is not a claim about the active network version.

## Related

- [[Notes/Blockchain/Solana overview|Solana overview]]
- [[Notes/Systems/Byzantine faults|Byzantine faults]]

## Sources

- [Original Solana whitepaper](https://solana.com/solana-whitepaper.pdf)
- [Solana Alpenglow upgrade](https://solana.com/nl/upgrades/alpenglow)
