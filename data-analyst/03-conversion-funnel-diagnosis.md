## Conversion funnel diagnosis

`⏱️ ~1 min read`

> **🎯 Result:** I used funnel analysis to find exactly where a SaaS platform was losing customers, and reframed a vague "acquisition problem" into a specific, data-backed diagnosis.

<details>
<summary><b>🧩 Situation</b> — a sharp drop in paying customers, and pressure to just spend more on acquisition</summary>

A self-serve SaaS platform saw a sharp, sustained drop in new paying customers over several months. There was no clear owner of "why," and pressure to simply spend more on acquisition instead of investigating the actual cause.

</details>

<details>
<summary><b>⚙️ What I did</b> — 2 steps: break the funnel into stages, measure each one</summary>

- Used the funnel view described in the [GA4-to-BigQuery pipeline case study](./01-ga4-bigquery-pipeline.md) to break the customer journey into clear stages: visit, registration, product created, product published, paid.
- Measured each stage separately and found the drop was not spread evenly across the funnel. Most users who registered successfully created something in the product, a much smaller share published it, and almost none converted to a paying plan.

</details>

**📈 Result.** Reframed the conversation from "we have an acquisition problem, spend more on marketing" to "we have an activation and monetization problem." This redirected the team's roadmap toward the actual bottleneck and delivered measurable, actionable insights instead of more unfocused spending.

🏷️ `Funnel Analysis` `SQL` `Root-Cause Analysis` `Translating Data into Business Recommendations`

---
[← Back to Data Analyst case studies](./README.md)
