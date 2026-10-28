# CI delivery and deployment

Map: [[Maps/Systems|Systems]]

## Summary

Continuous integration validates changes frequently. Continuous delivery keeps changes releasable; continuous deployment automatically releases passing changes.

## Key points

- CI commonly builds and runs checks for a proposed change.
- Delivery can include a manual production release decision.
- Deployment automates that release step after the required gates pass.
- Keep secrets in the deployment platform's secret mechanism, and design rollback and monitoring alongside release automation.

## Related

- [[Notes/Python/CI CD Basics|CI CD Basics]]
- [[Notes/Systems/Containers and orchestration|Containers and orchestration]]
