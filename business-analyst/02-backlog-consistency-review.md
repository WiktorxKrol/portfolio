## Backlog consistency and traceability review

`⏱️ ~90 sec read`

> **🎯 Result:** I found three real, silent gaps in a fast-growing backlog by checking requirements against each other, not just one at a time — and closed all three before they reached a sprint.

<details>
<summary><b>🧩 Situation</b> — a 45-item backlog grown fast enough to hide gaps between requirements</summary>

A backlog for a new product had grown quickly to around 45 items across multiple epics, written over a short period. Backlogs written fast are exactly where silent gaps hide: a frontend flow that promises a step no backend task actually delivers, or two similar flows that behave inconsistently without anyone noticing.

</details>

<details>
<summary><b>⚙️ What I did</b> — 3 gaps found by cross-referencing, then closed</summary>

Reviewed every requirement against its neighbors, not in isolation, and found:

1. A frontend flow that explicitly promised "send the contract to the tenant for approval, then activate it," with no backend task anywhere that actually implemented tenant-side approval or the activation step.
2. Two nearly identical flows (contract termination and contract amendment) where one included a tenant notification as part of the requirement, and the other silently did not — an inconsistency that would only surface after launch.
3. A technical dependency (e-signature validity) that one task flagged as "pending legal confirmation," but no legal task in the backlog actually asked that question — it existed as an unowned assumption.

Then closed all three: wrote the missing backend task, aligned the two inconsistent flows to the same notification behavior, and added the missing legal question to the right owner's queue instead of leaving it as an unstated assumption.

</details>

**📈 Result.** All three gaps were closed before reaching a sprint, instead of being discovered by an engineer mid-build, or by a customer in production.

🏷️ `Requirements Traceability` `Cross-Referencing for Logical Completeness` `Gap Analysis` `Attention to Detail`

---
[← Back to Business Analyst case studies](./README.md)
