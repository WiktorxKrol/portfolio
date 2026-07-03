# Coordinating an external partner integration against a hard deadline

**Context:** An integration between our platform and a large external marketplace partner had to be functional before a real-world, date-fixed event — complicated by the partner's own team going on leave right before that date, with credentials and access scattered across several different partner-side owners.

**Problem:** No single person on the partner side could hand over everything at once. Waiting for a coordinated handoff meeting would have missed the window entirely.

**What I did:**
- Built a checklist of every external dependency blocking the integration (API keys, staging credentials, cloud environment access, which repository the work should live in), each with a named owner and an urgency flag.
- Chased each item individually and in parallel rather than waiting for one meeting to resolve all of them.
- Kept a visible running list of what was resolved vs. still blocking, so the team always knew exactly what was standing between them and a working integration.

**Outcome:** Every blocking access item was cleared before the partner's team went on leave, and the integration was functional ahead of the fixed external deadline.

**Skills:** external stakeholder management, parallelized blocker-chasing, working a hard deadline backwards into a checklist.
