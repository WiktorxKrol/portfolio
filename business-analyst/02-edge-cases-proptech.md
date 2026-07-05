## Edge case discovery for a rental property management app

I start looking for edge cases before developers ask questions. That's the point - if a developer is asking, I'm already late.

Happy paths are easy. Anyone can plan a happy path by looking at a design. The hard part is sad paths: what breaks this flow, who owns it when it breaks, and what should the system do about it.

---

**Why rental platforms have more edge cases than most.**

A rental platform has multiple user roles interacting with the same data. A landlord and a tenant both touch the same contract, the same payment, the same property. When their actions conflict or overlap, the system needs a defined answer.

Some examples from this project:

- **Tenant with two roles** - a person can be a tenant in one property and a property manager in another. That's one account, two permission contexts. The system needs to handle that without mixing them up.
- **Partial rent payment** - a tenant pays 80% of the monthly rent. Does the system accept it, reject it, or record it as a debt? What notification goes to the landlord? There's no universally correct answer - but there has to be a defined one.
- **Disputed handover protocol** - landlord and tenant submit different meter readings at move-in. Which one is authoritative? Who can override? What's the audit trail?
- **Expired invitation link** - a landlord invites a tenant, the tenant clicks the link days later. Does it still work? Does re-sending create a duplicate account?
- **Contract flow without a tenant** - the app generates rental contracts, but there was no flow for how the tenant receives, accesses, or signs it. I designed that flow from scratch because it didn't exist in the inherited designs.

For questions that were legal rather than product decisions - e-signature validity, statutory deposit limits - I flagged them to external legal counsel instead of writing an assumption into the spec.

---

**How I work on edge cases.**

I use AI. I feed it the project context and design, and generate a list of edge cases. Then I go through them: verify which are real, eliminate duplicates, identify which need a business decision versus a technical one. The AI speeds up the generation. The judgment on what to do about each one is mine.

Every edge case that matters ends up as a scoped task in the backlog - not a separate document that nobody reads. Each task has an owner, a status, and acceptance criteria.

---

**Skills:** edge case analysis, AI-augmented requirements discovery, UML/BPMN, business rule definition, legal routing, backlog integration.
