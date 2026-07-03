# Conversion funnel diagnosis

**Context:** A self-serve SaaS platform saw a sharp, sustained drop in new paying customers over several months, with no clear owner of "why" and pressure to just spend more on acquisition.

**Problem:** "Acquisition dropped" is not an actionable statement — it could mean fewer visitors, fewer signups, fewer people finishing onboarding, or fewer people converting to paid, and each of those implies a completely different fix.

**What I did:**
- Used the funnel view described in the [GA4 → BigQuery pipeline case study](./01-ga4-bigquery-pipeline.md) to break the funnel into its actual stages: visit → registration → product created → product published → paid.
- Isolated exactly where the drop was concentrated: the large majority of registered users successfully created something in the product, a much smaller fraction published it, and almost none converted to a paying plan — the drop was not evenly spread across the funnel, it was concentrated at the activation and monetization stages.

**Outcome:** Reframed the conversation from "we have an acquisition problem, spend more on ads" to "we have an activation/monetization problem," which redirected the team's actual roadmap toward fixing the real bottleneck instead of pouring more traffic into a leaky funnel.

**Skills:** funnel decomposition, distinguishing correlation from the actual point of failure, translating a vague business complaint into a specific, data-backed diagnosis.
