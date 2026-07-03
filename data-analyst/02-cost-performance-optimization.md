# BigQuery cost & performance optimization

**Context:** Dashboards querying raw GA4 daily-sharded tables directly, on a dataset that grows every day.

**Problem:** Querying raw event-level data straight from a dashboard gets slower and more expensive every day the underlying table grows, and it's the kind of cost that creeps up silently until someone notices the bill.

**What I did:**
- Built a scheduled query that runs once daily and pre-aggregates raw events into summary tables, so dashboards query a small aggregate instead of scanning raw history every time they load.
- Replaced wildcard table scans (`events_*`) with `_TABLE_SUFFIX BETWEEN` date-bounded scans wherever a query only needed a known date range.
- Enforced column pruning — selecting only the columns a query actually needed instead of `SELECT *` — and clustered aggregate tables by `event_name`, the most common filter predicate.

**Outcome:** Dashboard load times became predictable and cost stopped scaling with the size of the full historical dataset.

**Skills:** BigQuery cost model (bytes scanned, not rows), scheduled query design, clustering/partitioning strategy, translating "slow dashboard" complaints into a specific bytes-scanned root cause.
