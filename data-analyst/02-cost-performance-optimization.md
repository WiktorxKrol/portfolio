## BigQuery cost and performance optimization

> **In one line:** I redesigned how dashboards query BigQuery so cost stopped scaling with the size of the full historical dataset, and load times became predictable.

**Situation.** Dashboards were querying raw, daily-sharded GA4 tables directly, on a dataset that grows every day. This gets slower and more expensive as the table grows, and the cost tends to creep up silently until someone notices the bill.

**What I did.**
- Built a scheduled query that runs once a day and pre-aggregates raw events into summary tables, so dashboards query a small, ready-made table instead of scanning the full raw history every time they load.
- Replaced full-table wildcard scans with date-bounded scans wherever a query only needed a specific, known date range.
- Enforced column selection best practices (never selecting unnecessary columns) and organized the aggregate tables by the most common filter field, to speed up queries further.

**Result.** Dashboard load times became fast and predictable, and query cost stopped scaling with the size of the full historical dataset — a clear, measurable, scalable improvement.

**Skills:** BigQuery cost optimization, SQL performance tuning, scheduled query design, data warehousing best practices.
