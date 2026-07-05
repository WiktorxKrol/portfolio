# Business Analyst

I'm the only person writing specifications at Ulan Software. Every requirement that reaches a 15-person dev team goes through me, across 4 products and 2.5 years.

---

## Specifications

When I joined Ulan, specs existed but had no acceptance criteria and no edge cases. Developers stopped to ask questions constantly - at peak I was answering up to 8 people at the same time every day.

I made a different call: spend more time on the spec upfront, don't field questions for two weeks after. There are now days where no developer writes to me at all.

Every feature that enters a sprint has a written spec covering:

- **Acceptance criteria** - exact conditions a developer can verify the task is done
- **Edge cases** - what happens when something goes wrong, is missing, or conflicts with another rule
- **Business rules** - written explicitly, not implied by the design
- **Out of scope** - what is explicitly not part of this task

The out-of-scope section matters more than it sounds. Without it, developers make judgment calls. Sometimes they build more than needed. Sometimes the wrong thing. Writing "this does not include X" removes that ambiguity.

**Example from e-commerce checkout:** the happy path is obvious. The spec had to answer: what happens if payment succeeds but the confirmation email fails? What if the user has two tabs open and completes checkout in both? What if a product goes out of stock between adding to cart and paying? Each of those surfaces in production if it's not in the spec.

---

## Edge cases

Happy paths are easy. Anyone can plan a happy path by looking at a design. The hard part is sad paths: what breaks this flow, who owns it when it breaks, and what should the system do about it.

I start looking for edge cases before developers ask. If a developer is asking, I'm already late.

**Examples from the proptech app (rental property management):**

- **Tenant with two roles** - a person is a tenant in one property and a property manager in another. One account, two permission contexts.
- **Partial rent payment** - tenant pays 80% of monthly rent. Accept, reject, or record as debt? What notification goes to the landlord?
- **Disputed handover protocol** - landlord and tenant submit different meter readings at move-in. Which is authoritative? Who can override?
- **Expired invitation link** - landlord invites a tenant, tenant clicks days later. Does it work? Does re-sending create a duplicate account?
- **Missing tenant flow** - the app generated rental contracts but had no flow for how the tenant receives, accesses, or signs one. I designed that flow from scratch because it didn't exist in the inherited designs.

Questions that were legal rather than product decisions - e-signature validity, deposit limits - I flagged to external legal counsel instead of writing an assumption into the spec.

**How I work on edge cases:** I use AI to generate a candidate list from the project context and design, then verify, filter, and decide what to do with each one. The AI speeds up generation. The judgment is mine.

Every edge case ends up as a scoped task in the backlog with an owner, status, and acceptance criteria - not a separate document nobody reads.

---

**Skills:** specification writing, acceptance criteria, edge case analysis, UML, BPMN, business rule definition, legal routing, AI-augmented requirements discovery.
