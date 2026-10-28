# Microservices and monoliths

Map: [[Maps/Systems|Systems]]

## Summary

Deployment boundaries are a design choice. A monolith can contain well-separated modules; microservices introduce independently deployed components and network boundaries.

## Key points

- Separate services can support independent ownership and scaling when the boundaries fit the domain.
- Remote calls introduce latency, partial failure, retries, and consistency problems.
- A service split does not automatically remove coupling; shared data and release dependencies can preserve it.
- Prefer boundaries that solve an observed problem, rather than treating either architecture as universally better.

## Related

- [[Notes/Systems/Containers and orchestration|Containers and orchestration]]
- [[Notes/Systems/Concurrency and parallelism|Concurrency and parallelism]]
