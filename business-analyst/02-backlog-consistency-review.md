# Backlog consistency & traceability review

**Context:** A backlog for a new product had grown quickly — around 45 items across multiple epics, written over a short period. Fast-written backlogs are exactly where silent gaps hide: a frontend flow that promises a step no backend task actually implements, or two near-identical flows that behave inconsistently without anyone noticing.

**Problem:** Individually, every ticket looked reasonable. The problem only shows up when you read them against each other.

**What I did — read every requirement against its neighbors, not in isolation — and found:**
1. A frontend flow that explicitly promised "send the contract to the tenant for approval, then activate it," with no backend ticket anywhere that actually implemented tenant-side approval or the activation trigger.
2. Two near-identical flows (contract termination vs. contract amendment) where one notified the affected party as part of its spec and the other silently didn't — an inconsistency that would only surface in production.
3. A technical dependency (e-signature validity) that one ticket flagged as "pending legal confirmation," but no legal ticket in the backlog actually asked the question — it existed as an assumption with no owner.

**What I did about it:** wrote the missing backend ticket, aligned the two inconsistent flows to the same notification behavior, and added the missing legal question to the right owner's queue instead of leaving it as an unstated assumption.

**Outcome:** All three gaps were closed before they reached a sprint, instead of being discovered by an engineer mid-implementation or, worse, by a user in production.

**Skills:** cross-referencing requirements for logical completeness rather than reviewing tickets one at a time, spotting silent inconsistency between superficially similar features, distinguishing a confirmed requirement from an unstated assumption.
