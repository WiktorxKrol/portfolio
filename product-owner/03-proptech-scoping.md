## Scoping a proptech app - picking up where someone left off

I inherited this project. What I got: incomplete design files and partial requirements from a colleague. The product is a rental property management app - landlords, tenants, property managers, all in one platform.

The gap I found immediately: everything had been designed from the landlord's perspective. The tenant didn't exist in the designs.

---

**What that meant in practice.**

The landlord side had UI designs. The tenant side had nothing. That's not a small gap - in a rental platform, the tenant is half the product. Every flow that landlords initiate has to land somewhere on the tenant's end.

I worked through the landlord flows and mapped what was missing on the tenant side. One example: the contract flow. The app has a contract generator - landlords can create rental agreements. But there was no flow for how the tenant receives the contract, accesses it, or signs it. The landlord flow ended at "contract generated" with nowhere for that contract to go.

I designed the tenant side of that flow myself - invitation, access, signing - based on competitive benchmarking and business logic. I didn't ask the investor what it should look like. I proposed it, we discussed it, and it went into the backlog.

I did this for several missing flows. Each time the same process: identify the gap, benchmark how others solve it, propose a solution, align with the investor.

---

**The broader scoping work.**

Beyond filling the tenant gaps, I was responsible for the full backlog: ~70 tasks across 12 epics, roughly 570 hours of planned work. I sequenced them by dependency - authentication before contracts, contracts before payments.

I also documented 80+ edge cases before development started. The ones that come up in rental platforms are genuinely complicated: a tenant who is also a property manager in another property needs two separate permission contexts in the same account. A partial rent payment needs a decision - accept, reject, or flag as debt. These aren't edge cases you can leave for engineering to figure out mid-sprint.

Where questions were legal rather than product decisions - e-signature validity, statutory deposit limits - I flagged them explicitly and routed them to external legal counsel instead of writing an assumption into the spec.

---

**Skills:** scope gap analysis, flow design from scratch, competitive benchmarking, stakeholder alignment, edge case documentation, UML/BPMN, legal routing, dependency-based backlog sequencing.
