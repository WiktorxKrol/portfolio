# Running multiple products at different lifecycle stages simultaneously

**Context:** Owned product decisions across four concurrent efforts at once: a mature SaaS product with an active e-commerce release and real technical debt, a second mature product, a brand-new product being built from zero, and a client-facing integration with an external marketplace partner on a hard deadline.

**Problem:** Each of these needs a fundamentally different operating mode. Treating them the same way means either the mature product's bug backlog rots, or the new product never gets scoped, or the partner integration misses its deadline because nobody's chasing external blockers daily.

**What I did:**
- Mature product: tracked and triaged priority-1 bugs per engineer, kept a running view of who owned what and how much was overdue, and pushed a coordinated close-out before a release deadline.
- New product (0→1): ran it as a scoping exercise, epic by epic, with its own separate pacing (see [zero-to-one case study](./01-zero-to-one-launch.md)).
- Partner integration: ran it as a checklist of external dependencies with named owners, chased individually, because a single "coordinated handoff" meeting wasn't going to happen before the partner's team went on leave.
- Used different cadences deliberately: capacity math and sprint hygiene for the mature product, dependency-ordered epics for the new one, daily blocker-chasing for the partner integration.

**Outcome:** All four kept moving without any one of them silently stalling because it wasn't "today's" focus. Each got the operating rhythm it actually needed instead of one-size-fits-all process.

**Skills:** context-switching between very different operating modes, playbook selection per product stage, protecting attention across competing priorities.
