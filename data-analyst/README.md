# Data Analyst

---

## GA4 + BigQuery - from unused data to a decision that changed onboarding

GA4 was running on BOWWE. Nobody was using it beyond the basics.

I wanted to know what was actually happening with users - conversion rate, how often they logged in, which pages they visited before signing up, whether the pricing page converted. The GA4 interface gave surface-level numbers but couldn't answer the question I cared about most: what does the full journey look like, from first visit to paid plan, for a single user?

GA4 tracks anonymous sessions before login and assigns a pseudo ID. Our database has a real user ID after signup. Those two are disconnected by default. I read that you can join them in BigQuery on the session where the signup event fires - so that's what I built.

**What I found:**

Churn was at around 12%. Industry benchmark for SaaS is under 5%. That was the first number that made people pay attention.

I found a correlation between number of logins and the probability of buying a paid plan. Going from 1 login to 6 logins made a user 8x more likely to purchase. That's a signal strong enough to reorganize priorities around.

Users weren't publishing their sites fast enough. The time between registration and first publish was longer than it should be, and users who didn't publish early rarely came back.

**What changed:**

I brought these findings to the CEO and marketing team. The goal became: get the user into the builder and to their first published site as fast as possible. We cut interruption screens, unnecessary modals, steps that added friction before the user had seen any value. If 6 logins means 8x more likely to buy, the job is to give users a reason to come back 6 times.

**How this was built:**

I'm not a data engineer. I understood the problem, knew what questions I needed to answer, and used AI to accelerate the implementation - writing and debugging SQL, understanding the GA4 export schema (`RECORD REPEATED` fields that require `UNNEST` to query), structuring the BigQuery views. The thinking, the questions, and the decisions are mine. The speed came from AI.

Output: BigQuery views and a Data Studio dashboard that marketing and leadership check without asking me for a report.

---

## Product health metrics that drove the e-commerce decision

BOWWE had growing signups but no reliable view of what happened after registration. Management and marketing were making decisions on partial information.

I built SQL queries against our product database tracking:

- **Registrations** - new users per day/week/month, by acquisition channel
- **Project creation rate** - how many registered users actually built something
- **Registration-to-paid conversion** - how many upgraded, and how long it took
- **Churn** - cancellations per period and at what point in the subscription lifecycle
- **Retention** - active users after 7, 30, and 90 days
- **LTV** - average revenue per user over subscription lifetime, by plan

The data showed high registrations, low conversion to paid. I cross-referenced with our onboarding survey. Around 40% of users said they came to build an online store. BOWWE had no e-commerce. Those users registered, couldn't do what they came to do, and left.

That combination - conversion data plus survey - made the case for building the e-commerce module. Not "users are asking for it," but "we can see exactly how many users we're losing and why." The module went from far out on the roadmap to the next major project.

I exposed these metrics as views feeding directly into Data Studio dashboards, so management and marketing could check them without coming to me every time.

---

**Skills:** SQL, BigQuery, GA4, Data Studio, funnel analysis, churn analysis, retention, LTV, AI-augmented implementation, translating data into product decisions.
