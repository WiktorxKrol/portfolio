## Edge case discovery for a rental property management app

> **In one line:** I documented 80+ edge cases across 10 modules of a new proptech app before engineering started — so the difficult "what happens if…" questions were answered before anyone wrote a line of code.

**Situation.** A rental property management app (for landlords, tenants, and property managers) existed only as a design mockup. Every core flow had a clear happy path in the mockup — contract signing, deposits, notice periods, maintenance requests, meter readings, marketplace bookings. None of them had answers for failure states, conflict states, or ambiguous real-world situations.

**What I did.**

Reviewed every flow systematically — not just "does this make sense on screen" but "what breaks this, and who owns it when it breaks."

Examples of edge cases documented:

- **Disputed handover protocol** — tenant and landlord both submit different meter readings at move-in. Which one is authoritative? Who can override? What's the audit trail?
- **Partial rent payment** — tenant pays 80% of the monthly rent. Does the system accept it, reject it, or flag it as a debt? What notification goes to the landlord?
- **Tenant with two roles** — a person is both a tenant in one property and a property manager in another. The system needs two separate permission contexts for the same account.
- **Expired invitation link** — a landlord invites a tenant, but the tenant clicks the link 5 days later. What happens? Does re-sending create a duplicate account?
- **E-signature validity** — is a digitally signed contract via our platform legally enforceable in the target jurisdiction? This is not a product decision — I flagged it to external legal counsel instead of letting engineering assume the answer.

**How I organized the output.**

Every edge case was written as a scoped task in the backlog — not a separate document that would get ignored. Each task had an owner, a status, and acceptance criteria. Legal-dependent items were tagged as "pending legal confirmation" with a named contact responsible for the answer.

I also created UML and BPMN diagrams for the core flows, so the team had a shared visual model — not just a list of text rules.

**Result.** Engineering started with a backlog where the hard questions were already answered. No engineer had to make a judgment call on a business rule mid-sprint. Legal questions were in the right queue, not silently embedded in a spec.

**Skills:** edge case analysis, requirements elicitation, UML, BPMN, business rule definition, legal routing, backlog structuring.
