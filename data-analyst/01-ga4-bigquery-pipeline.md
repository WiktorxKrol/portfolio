## GA4 + BigQuery - from unused data to a decision that changed onboarding

GA4 was running on BOWWE. Nobody was using it beyond the basics.

I wanted to know what was actually happening with users - conversion rate, how often they logged in, which pages they visited before signing up, whether the pricing page converted. The GA4 interface gave surface-level numbers but couldn't answer the question I cared about most: what does the full journey look like, from first visit to paid plan, for a single user?

The problem is that GA4 tracks anonymous sessions before login and assigns a pseudo ID. Our database has a real user ID after signup. Those two are disconnected by default. I read that you can join them in BigQuery on the session where the signup event fires - so that's what I built.

---

**What I found.**

Churn was at around 12%. Industry benchmark for SaaS is under 5%. That was the first number that made people pay attention.

The second finding was about login frequency. I found a correlation between number of logins and the probability of a user buying a paid plan. Going from 1 login to 6 logins made a user 8x more likely to purchase. That's not a small effect - that's a signal strong enough to reorganize priorities around.

The third: users weren't publishing their sites fast enough. The time between registration and first publish was longer than it should be, and users who didn't publish early rarely came back.

---

**What changed.**

I brought these findings to the CEO and marketing team. We worked on onboarding. The goal became simple: get the user into the builder and to their first published site as fast as possible, removing everything in the way.

We cut interruption screens, unnecessary modals, steps that added friction before the user had seen any value. The logic: if 6 logins means 8x more likely to buy, the job is to give users a reason to come back 6 times - and that starts with making the first session worth returning for.

---

**How this was built.**

I'm not a data engineer. I understood the problem, knew what questions I needed to answer, and used AI to accelerate the implementation - writing and debugging SQL, understanding the GA4 export schema (`RECORD REPEATED` fields that require `UNNEST` to query), structuring the BigQuery views. I also read a lot. I learn something new every day and this project gave me plenty of reasons to.

The thinking, the questions, and the decisions that came out of the data are mine. The speed came from AI.

The output: a set of BigQuery views and a Data Studio dashboard that marketing and leadership check without asking me for a report.

---

**Skills:** BigQuery, SQL, GA4 export schema, session reconstruction, funnel analysis, churn analysis, Data Studio, translating data into product decisions.
