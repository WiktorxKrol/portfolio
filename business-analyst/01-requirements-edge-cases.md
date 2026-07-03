# Requirements & edge case discovery for a new product

**Context:** A brand-new SaaS product (property rental management) at the concept stage — a design mockup and a strategy document, nothing else.

**Problem:** Nothing had been formally specified. Every core flow (contract signing, deposits, notice periods, maintenance requests, meter readings, marketplace bookings) had obvious happy-path behavior in the mockup, but no answer for what happens when things don't go as planned.

**What I did:**
- Walked every core flow and systematically catalogued 80+ edge cases across 10 functional modules — what happens on a disputed handover protocol, a partial rent payment, an expired invitation link, a tenant with two active roles, and so on.
- Extracted explicit business rules where the mockup only implied behavior (e.g., what counts as a payment default, what the default notice period is) and documented them as named, referenceable rules rather than leaving them as tribal knowledge.
- Flagged the subset of business rules that were genuinely legal questions (contract validity, statutory deposit limits, e-signature validity) rather than product decisions, and routed them to outside legal counsel instead of guessing.
- Fed the edge cases directly into the engineering backlog as scoped tasks, not as a separate document nobody would read.

**Outcome:** Engineering started building against a backlog with the ambiguous "what happens if..." questions already answered, instead of discovering them mid-sprint. Legal-dependent assumptions were explicitly labeled as assumptions pending confirmation, not silently treated as fact.

**Skills:** requirements elicitation from unstructured source material (mockups, strategy docs), edge-case enumeration, extracting implicit business rules and making them explicit, distinguishing product decisions from legal questions.
