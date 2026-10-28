# React state and effects

Map: [[Maps/Web development|Web development]]

## Summary

React calculates UI from props and state. Effects synchronize a component with an external system after rendering.

## Key points

- Call Hooks in the supported top-level order, not conditionally in ordinary component code.
- A state setter schedules an update; keep render calculations pure.
- Effects should declare the reactive values they use and return cleanup when connecting to external resources.
- Portals place rendered content in another DOM location while preserving its React parentage.

## Related

- [[Notes/Web/React rendering|React rendering]]
- [[Notes/Web/React composition|React composition]]
