# Monitoring and Caching

Map: [[Maps/Python|Python]]

## Summary

Keeping a running production app fast and observable: caching expensive results, tracking health via metrics.

## Key points

- Caching layers: in-process (lru_cache), or external (Redis) for shared/multi-process caching
- Cache invalidation is famously hard - pick a clear expiry (TTL) or invalidation trigger upfront
- Metrics (request latency, error rate) plus logging together give observability - see [[Notes/Python/Logging|Logging]]
- Health-check endpoints let orchestrators (Docker/Kubernetes) know if an instance is alive

## Practice

- [ ] Add a Redis-backed cache in front of a slow database query
- [ ] Set a TTL-based cache expiry and explain what happens after it expires
- [ ] Add a /health endpoint to a simple API

## Related

- [[Notes/Python/Logging|Logging]]
- [[Notes/Python/Functools and Itertools|Functools and Itertools]]
- [[Notes/Python/Dockerizing Python Apps|Dockerizing Python Apps]]
