# Proximity search design

Map: [[Maps/Systems|Systems]]

## Summary

A proximity service finds businesses near a coordinate and radius. A spatial index narrows candidate locations before an exact distance filter.

## Key points

- Separate business details from location-search access patterns. Reads may be much more frequent than business updates.
- Example assumptions: 100 million daily users × 5 queries per day gives about 5,800 average queries/second; peak traffic needs a separate estimate.
- At 200 million businesses and 1 KB of details each, raw detail storage is roughly 200 GB, before indexes, replicas, and overhead.
- Geohashes divide space into cells; query relevant neighboring cells as well as the containing cell. Required coverage depends on radius and precision.
- Spatial trees and database spatial indexes are alternatives. Do not assume separate latitude/longitude comparisons provide a complete efficient radius search.
- Replication lag, caching, pagination, and update freshness are explicit tradeoffs.

## Related

- [[Notes/Systems/Database keys|Database keys]]
- [[Notes/Systems/Consistent hashing|Consistent hashing]]

## Sources

- [Original lecture](https://www.youtube.com/watch?v=M4lR_Va97cQ)
