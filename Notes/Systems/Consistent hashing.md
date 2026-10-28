# Consistent hashing

Map: [[Maps/Systems|Systems]]

## Summary

Consistent hashing maps keys and nodes into the same logical space so membership changes move a limited portion of the key assignments.

## Key points

- With `hash(key) % N`, changing the number of nodes changes many assignments.
- In a ring design, hash a key and select its successor node, wrapping around the ring when needed.
- Multiple virtual positions per physical node can improve distribution. They do not guarantee equal real-world load.
- Replication, failure detection, and migration of stored values are additional design concerns.

## Related

- [[Notes/Systems/Microservices and monoliths|Microservices and monoliths]]

## Sources

- [Original lecture](https://www.youtube.com/watch?v=UF9Iqmg94tk)
