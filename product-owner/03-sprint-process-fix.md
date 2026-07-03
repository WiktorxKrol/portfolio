# Fixing a broken sprint process

**Context:** A ~15-person engineering team whose sprint process had quietly stopped working — inconsistent estimation, unclear sprint-boundary rules, and backlog debt silently rolling forward sprint after sprint without anyone noticing the pattern.

**Problem:** Capacity numbers looked fine on paper but didn't reflect reality — unestimated work was invisible in planning, "sprint end" meant whatever due-date happened to be sitting in the tracker, and work in review/testing was being shuffled between sprints as if it were still open, hiding how much was actually stuck.

**What I did — a small number of hard rules instead of a process overhaul:**
- Unestimated tickets get a fixed placeholder value in capacity math, so they show up as a cost instead of disappearing from the total.
- Sprint boundary is a fixed day and time, not whatever due-date is in the tracker — removes the ambiguity that let work quietly slip.
- Only genuinely open work moves between sprints. Work sitting in review, testing, or code-review never gets moved — moving it papered over the fact that it wasn't actually progressing.
- Set and tracked an explicit committed throughput floor for the team's most chronically overdue work area, so "we'll get to it" had a number attached.

**Outcome:** Capacity numbers became trustworthy again — planning reflected what the team could actually deliver, not what the tracker's due-dates implied. The chronically overdue work area started closing a minimum number of items every sprint instead of zero.

**Skills:** process diagnosis, choosing minimal high-leverage rules over a full re-org, making invisible debt visible.
