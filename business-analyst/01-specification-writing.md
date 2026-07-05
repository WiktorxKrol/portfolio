## Writing specifications as the sole BA in a 20-person SaaS team

> **In one line:** I'm the only person writing specifications at Ulan Software — every requirement that reaches engineering goes through me, across four products and 2.5 years.

**Situation.** At Ulan, there is no dedicated BA team. When I joined as Product Owner, specifications either did not exist or were written informally. Engineers were making assumption calls on their own — which worked until it didn't. I took full ownership of the specification process across all products.

**What this looks like in practice.**

Every feature that enters a sprint has a written spec before it's groomed. A spec at Ulan contains:

- **Functional description** — what the feature does and why it exists
- **Acceptance criteria** — exact conditions an engineer can verify the task is done
- **Edge cases** — what happens when input is missing, invalid, or in conflict with another rule
- **Business rules** — named, explicit rules (e.g. "a tenant invitation link expires after 48 hours") rather than implied behaviour
- **Out of scope** — what is explicitly not part of this task, to prevent scope creep mid-sprint

**A concrete example from the e-commerce module.**

The checkout flow had an obvious happy path — user adds items, enters address, pays, gets confirmation. But the spec also had to answer: what happens if payment succeeds but the order confirmation email fails to send? What if the user has two browser tabs open and completes checkout in both? What if a product goes out of stock between adding to cart and paying? Each of those is a real scenario that surfaces in production if it's not answered in the spec.

**A concrete example from the proptech app.**

A "contract termination" flow and a "contract amendment" flow were written in different sessions. When I cross-referenced them, one included a tenant notification step and the other silently did not. Same trigger, different behavior — an inconsistency that would only surface after launch. I caught it during spec review and aligned both flows before they reached engineering.

**Result.** Over 2.5 years and 4 products, engineering has a consistent source of truth for requirements. Edge cases are answered in the spec, not discovered mid-sprint or post-launch.

**Skills:** specification writing, acceptance criteria, edge case analysis, business rule definition, requirements traceability.
