## Building product health metrics that drove the e-commerce decision

> **In one line:** I built SQL queries tracking registration-to-paid conversion, churn, retention, and LTV from our product database — and the data directly drove the decision to build a full e-commerce module.

**Situation.** BOWWE had a growing number of signups but no reliable view of what happened after registration. Did users actually build anything? Did they upgrade to a paid plan? Did they come back? Management, marketing, and I were making decisions based on partial information — mostly gut feel and surface-level GA4 data that stopped tracking users after signup.

**What I built.**

A set of SQL queries against our product database covering the core health metrics of the business:

- **Registrations over time** — how many new users signed up per day/week/month, segmented by acquisition channel
- **Project creation rate** — of users who registered, how many actually created a project (the first activation step)
- **Registration-to-paid conversion** — how many users upgraded to a paid plan, and how long it took them from signup
- **Churn** — how many paying users cancelled in a given period, and at what point in the subscription lifecycle
- **Retention** — what percentage of users were still active (logged in, opened a project) after 7, 30, and 90 days
- **LTV** — average revenue per user over their subscription lifetime, segmented by plan

I exposed these as views that fed directly into Data Studio dashboards, so management and marketing could check them without coming to me every time.

**How the data drove a real decision.**

The numbers showed a clear pattern: a high volume of users were registering, but the conversion rate to paid plans was low. We had a hypothesis — but a hypothesis is not a decision.

To find out why, I cross-referenced the conversion data with results from our onboarding survey. The survey asked users what they were trying to build. A significant segment consistently answered: an online store. BOWWE at the time was a website and landing page builder — no e-commerce capability existed.

These users registered, couldn't do what they came to do, and left without paying.

That combination — low conversion rate in the data, e-commerce intent in the survey — made the case for building the e-commerce module. Not "users are asking for it," but "we can see exactly how many users we're losing and why."

**Result.** The e-commerce module was prioritized and built. The data gave the decision a concrete basis instead of a feature request. I also use the same health metrics on an ongoing basis to track whether product changes actually move the numbers.

**Skills:** SQL, product funnel analysis, retention analysis, churn analysis, LTV, Data Studio, connecting quantitative data to qualitative research.
