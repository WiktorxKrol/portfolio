## Building a GA4-to-BigQuery analytics pipeline from scratch

> **In one line:** I set up BigQuery and built a pipeline that joins website analytics (GA4) with internal business data — because a colleague had GA4 running but no one was doing anything with the data, and we were making product decisions by guessing.

**Situation.** A colleague had set up GA4 tracking on BOWWE. The raw data was there, but it lived in GA4's interface — disconnected from our internal database (the source of truth for signups, published sites, and revenue). Product and growth teams had no reliable way to see where users actually dropped off in the funnel.

Two problems made GA4 alone unreliable:
1. Ad blockers and consent choices make 10–15% of user behavior invisible to GA4.
2. GA4 cannot be trusted for revenue metrics — it misses too many conversion events.

The internal database was the opposite problem: it could tell you who paid, but not what they did before signing up.

**What I built.**

I set up the BigQuery project from zero and then built the pipeline:

- **Flattened the GA4 export.** GA4 stores event parameters as nested arrays (`RECORD REPEATED` fields). You cannot query them directly — every parameter requires an `UNNEST`. I wrote a clean view layer so analysts could query `page_location` or `session_id` without knowing the raw schema.

- **Connected anonymous to identified users.** GA4 assigns a random ID before login. Our database has a real user ID after signup. I joined them on the session where the signup event fired, so the full journey — from first visit to paid plan — links to one person.

- **Rebuilt sessions.** GA4's raw export does not give you session boundaries. I reconstructed sessions from the `ga_session_id` event parameter, grouping events into sessions with start times, end times, and page sequences.

- **Built a funnel view with a source split.** The funnel has two parts: early (visit → pricing page → registration) where GA4 is reliable, and late (registration → publish → paid) where the internal database is the source of truth. I joined them at the registration event — the one step both systems capture — to get a complete, trustworthy funnel in one view.

- **Built a weekly summary for non-technical stakeholders.** Leadership should not need to write SQL to see conversion rates. I created a summary view that feeds directly into a BI dashboard — updated automatically, no manual export.

**Why this mattered for product decisions.**

Before the pipeline, "where do users drop off?" was answered by gut feel or by whoever last looked at the GA4 interface. After the pipeline, product leadership had a specific answer every week — which step, how many users, how it changed after a release. Feature prioritization for onboarding improvements shifted from opinion to data.

**Result.** A working analytics pipeline used weekly by product leadership. Built from scratch — no existing BigQuery project, no existing data model, no existing documentation of the GA4 schema.

**Skills:** BigQuery setup, GA4 export schema, SQL, UNNEST, session reconstruction, funnel analysis, data pipeline design, BI dashboard integration.
