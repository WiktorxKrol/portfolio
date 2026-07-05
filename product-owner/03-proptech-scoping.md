## Scoping a proptech app from a design mockup

> **In one line:** I turned a design mockup and a strategy document into a 70-task backlog for a rental property management app — with 80+ edge cases documented before engineering started — while managing scope pressure from investors.

**Situation.** A new proptech app (rental property management for landlords, tenants, and property managers) existed only as a design mockup and a strategy document. Nothing had been scoped, estimated, or written as requirements. An external investor was involved, which added pressure to move faster than the process could realistically support.

**What I did.**

- Took full ownership of the scoping process: read every screen and every section of the strategy document, then converted them into ~70 scoped and estimated tasks covering business analysis, design, and engineering work — roughly 570 hours of planned effort.
- Organized the backlog into 12 epics (authentication, contract generation, payments, tenant panel, marketplace, and more) and sequenced them by technical dependency, so infrastructure was built before any feature that relied on it.
- Ran the scoping epic by epic with a stakeholder checkpoint after each one — deliberately avoiding dumping the full backlog at once, so the investor and team could review and adjust before the next piece was committed.
- Documented 80+ edge cases across all core flows before a single line of code was written: what happens with a disputed handover protocol, a partial rent payment, a tenant who has two roles in the system, an expired invitation link.
- Extracted implied business rules from the mockup — default notice periods, what counts as a missed payment, deposit calculation rules — and wrote them down explicitly so engineering did not have to guess.
- Identified which rules were actually legal questions (e-signature validity, statutory deposit limits, contract enforceability) and routed them to external legal counsel instead of treating them as product decisions.
- Created UML and BPMN diagrams for the core flows so the team had a shared, visual understanding of the process — not just a text description.

**Result.** Engineering started with a complete, reviewed backlog and answered edge cases. Legal-dependent items were clearly labeled as pending, not silently assumed. Stakeholder alignment was maintained throughout despite pressure to skip steps.

**Skills:** requirement scoping, edge case analysis, UML/BPMN, backlog structuring, dependency planning, legal routing, stakeholder management under pressure.
