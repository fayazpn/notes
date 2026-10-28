# Containers and orchestration

Map: [[Maps/Systems|Systems]]

## Summary

A container packages an application with a filesystem and runtime configuration. Orchestration manages multiple instances and their lifecycle.

## Key points

- A container shares the host kernel; it is not universally independent of the operating system or architecture.
- An image describes packaged files and startup behavior. A running container is an instance of that image.
- A Dockerfile commonly selects a base image, installs dependencies, copies code, chooses a user, and defines a command.
- Orchestration can schedule instances, restart failed workloads, and coordinate rollouts. Containers alone do not guarantee zero downtime.
- Load balancing distributes traffic using a defined policy such as round-robin or least-connections; CPU load is not always the deciding signal.

## Related

- [[Notes/Python/Dockerizing Python Apps|Dockerizing Python Apps]]
- [[Notes/Systems/Microservices and monoliths|Microservices and monoliths]]
