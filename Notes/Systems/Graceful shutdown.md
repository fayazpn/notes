# Graceful shutdown

Map: [[Maps/Systems|Systems]]

## Summary

Graceful shutdown stops accepting new work, gives current work a bounded chance to finish, and closes resources before the process exits.

## Key points

- Handle the termination signals relevant to the deployment, commonly SIGTERM and SIGINT.
- Stop accepting requests before closing resources needed by in-flight requests.
- Close database pools and long-lived connections after dependent work finishes, or after a defined deadline.
- Test timeout and forced-termination paths; shutdown handlers are not guaranteed to run on every kind of process exit.

## Related

- [[Notes/Go/HTTP handlers|HTTP handlers]]
- [[Notes/Systems/Database keys|Database keys]]
