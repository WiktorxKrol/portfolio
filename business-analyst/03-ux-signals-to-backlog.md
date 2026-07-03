# Turning quantitative UX signals into a prioritized backlog

**Context:** A session-recording/UX-analytics tool was generating rage-click, dead-click, and JS-error signals across a large web product, but nobody had a repeatable way to turn that raw signal into engineering work.

**Problem:** The data existed but wasn't actionable — a spreadsheet of "rage clicks by page" doesn't tell an engineer what to fix, and manually reviewing session recordings doesn't scale.

**What I did:**
- Built a repeatable process that pulls the tool's metrics via API, aggregates them per page/URL rather than per raw metric, and generates one clearly-scoped backlog item per problem area — "checkout button unresponsive on mobile, N rage-clicks/week" instead of a table of numbers.
- Worked within a hard daily API quota, so the process had to prioritize which pages to pull fresh data for versus rely on cache.

**Outcome:** UX friction became a normal, prioritized part of the backlog instead of a report nobody acted on.

**Skills:** turning ambiguous quantitative signal into scoped, actionable tickets; working within external API constraints; bridging analytics tooling and engineering process.
