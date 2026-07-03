## GA4-to-BigQuery analytics pipeline

> **In one line:** I built a pipeline that joins website analytics (GA4) and internal business data in BigQuery, giving leadership a single, trusted view of the customer journey.

**Situation.** A self-serve SaaS platform lets users sign up, build something, publish it, and pay. Product and growth teams had no reliable way to see where users actually dropped off, because GA4 (website analytics) and the internal database (business data, source of truth for revenue) were never connected. GA4 alone cannot be trusted for revenue, because ad blockers and consent choices make 10-15% of user behavior invisible to it. The internal database alone cannot explain anonymous behavior before signup.

**What I built.**
- Flattened the raw GA4 export into a clean, queryable view. GA4 stores event parameters as nested arrays (`RECORD REPEATED` fields), which require `UNNEST` to query at all.
- Connected the anonymous GA4 user ID to the internal, logged-in user ID, so anonymous and identified behavior link to the same person once they log in.
- Rebuilt user sessions from the session ID inside the event data, since GA4's export does not provide session boundaries directly.
- Built a daily funnel view that joins the two data sources exactly where each one is most reliable: GA4 covers the early steps (visit, pricing page, registration), and the internal database covers the later steps (registration, publish, paid), since GA4 loses too many of these users to tracking gaps to be trusted there.
- Added a weekly summary view for direct use in a BI dashboard, so non-technical stakeholders never had to write SQL to see the funnel and could make data-driven decisions on their own.

**Result.** A single, trusted view of where users actually drop off, used regularly by product leadership to prioritize onboarding improvements and deliver measurable results.

**Skills:** GA4 export schema, BigQuery view design, SQL, session reconstruction, data pipeline design, stakeholder reporting.
