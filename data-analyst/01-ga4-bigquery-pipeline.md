# GA4 → BigQuery analytics pipeline

**Context:** A self-serve SaaS platform where users move through: land on the site → sign up → build/publish something → pay. Product and growth had no reliable way to see where users actually dropped off, because GA4 (client-side, anonymous-friendly) and the internal database (server-side, revenue source of truth) were never joined.

**Problem:** GA4 alone can't attribute revenue reliably (ad blockers, consent choices, and client-side tracking gaps mean 10-15% of behavior is invisible to it). The internal database alone can't explain anonymous behavior before signup. Neither one told the whole story by itself.

**What I built:**
- Flattened the raw GA4 export (`events_*` daily-sharded tables) into a clean, queryable events view — GA4 exports `event_params` and `user_properties` as `RECORD REPEATED` (arrays of key-value structs), which need `UNNEST` to query at all.
- Joined `user_pseudo_id` (always present) to the internal `user_id` (present only once a user logs in), so anonymous and identified behavior connect to the same person once they authenticate.
- Reconstructed sessions from `ga_session_id` inside `event_params`, since GA4's export doesn't provide session boundaries directly — the unique key is `user_pseudo_id` + `ga_session_id`.
- Built a daily funnel view joining the two data sources at the point where each one is authoritative: GA4 covers visit → pricing-page view → registration (anonymous traffic), the internal DB covers registration → publish → paid (GA4 loses too many of these users to tracking gaps to be trusted here).
- Layered a weekly view with conversion rates on top for direct use in a BI/dashboarding tool, so non-technical stakeholders never had to write SQL to see the funnel.

**Outcome:** A single, trusted view of where users actually drop off — reconciling two data sources that previously told two different, unjoined stories — used regularly by product leadership to prioritize onboarding work.

**Skills:** GA4 export schema (nested `RECORD REPEATED`, `UNNEST`), BigQuery view design, session reconstruction, reconciling client-side and server-side data sources, translating raw event data into stakeholder-usable views.
