## Requirements and edge case discovery for a new product

> **In one line:** I catalogued 80+ edge cases and business rules for a new product before engineering started building, so ambiguous "what happens if..." questions were answered up front.

**Situation.** A new SaaS product (property rental management) existed only as a design mockup and a strategy document. Every core flow — contract signing, deposits, notice periods, maintenance requests, meter readings, marketplace bookings — had clear happy-path behavior in the mockup, but no answer for what happens when something goes wrong.

**What I did.**
- Reviewed every core flow in detail and documented over 80 edge cases across 10 functional modules: for example, what happens with a disputed handover protocol, a partial rent payment, an expired invitation link, or a tenant who has two different roles in the system.
- Extracted business rules that were only implied in the mockup — for example, what counts as a missed payment, or what the default notice period is — and wrote them down as named, referenceable rules instead of leaving them as unwritten assumptions.
- Identified which business rules were actually legal questions (contract validity, statutory deposit limits, e-signature requirements) and routed them to outside legal counsel, instead of letting engineering guess the answer.
- Fed every edge case directly into the engineering backlog as a scoped task, so the analysis led to action instead of sitting in a separate document.

**Result.** Engineering started building against a backlog where the difficult "what happens if..." questions were already answered. Legal-dependent assumptions were clearly labeled as pending confirmation, not treated as fact by mistake.

**Skills:** requirements elicitation, edge case analysis, business rule definition, cross-functional collaboration with legal and engineering.
