# Order table investigation

Map: [[Maps/CoinRoutes|CoinRoutes]]

## Summary

Verify how the order table combines initial loading with live updates before planning a transport change. The saved review supplies leads, not proof of the current component implementation.

## First question

What data does the table fetch initially, and what does each notification actually contain?

## Leads from the saved review

- Component name: `OrderTable`; AG Grid server-side data loading was mentioned.
- Data endpoint: `/api/sor_orders/`; detail fetching after notifications was also mentioned.
- Notifications: `CLIENT_ORDER_*` and `SOR_ORDER_*`.
- Scope identifiers: `strategyId`, `client_order_id`, and `parent_client_order_id`.
- Supporting concerns: column state, formatting, cached rows, permissions, and CSV export.

Verify those names and behaviors against the current source before relying on them.

## Investigation checklist

- [ ] Find the current component and datasource implementation; record file paths and symbols.
- [ ] Trace initial load, filters, pagination, and sort behavior.
- [ ] Inspect an actual message schema: notification, snapshot, or delta?
- [ ] Trace one update through formatting, storage/cache, and the grid API.
- [ ] Check duplicate/out-of-order events, reconnection, missed updates, and subscription cleanup.
- [ ] Confirm grid-library version and row-model constraints before choosing an update API.

## Decision to make after tracing

Can the socket supply all data and recovery behavior needed by the table, or should it remain a notification channel with a snapshot/refetch path?

## Related

- [[Notes/Systems/WebSockets|WebSockets]]
- [[Notes/Web/React state and effects|React state and effects]]
- [[Notes/Web/React component testing|React component testing]]
