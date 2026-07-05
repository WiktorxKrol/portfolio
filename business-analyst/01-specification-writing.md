## Writing specifications for a 15-person dev team - from daily interruptions to days of silence

When I joined Ulan, specifications existed but were incomplete. Bugs were documented reasonably well. New features weren't - no acceptance criteria, no edge cases, just a description of what the feature should do on a good day.

The CEO pushed for speed. Features were scoped fast and handed to engineering fast. The result was the opposite of fast: developers were constantly stopping to ask questions, and I was answering up to 8 people at the same time every day.

I made a different call. I'd rather spend more time on a spec upfront than field questions from 8 developers for the next two weeks. A developer who doesn't need to ask me anything is a developer who is building, not waiting.

---

**What changed.**

There are now days where no developer writes to me at all. That's 15 engineers working through a sprint without needing clarification on requirements. That doesn't happen by accident.

Every feature that enters a sprint has a written spec before grooming. The spec covers:

- What the feature does and why it exists
- Acceptance criteria - exact conditions the developer can verify the task is done
- Edge cases - what happens when something goes wrong, is missing, or conflicts with another rule
- Business rules written explicitly - not implied by the design, written down and named
- Out of scope - what is explicitly not part of this task

The last one matters more than it sounds. Without an explicit out-of-scope section, developers make judgment calls on what to include. Sometimes they build more than needed. Sometimes they build the wrong thing. Writing "this does not include X" removes that ambiguity.

---

**A concrete example from the e-commerce module.**

The checkout flow had an obvious happy path. The spec had to answer more than that: what happens if payment succeeds but the confirmation email fails to send? What if the user has two browser tabs open and completes checkout in both? What if a product goes out of stock between adding to cart and paying?

Each of those is a real scenario. Each of them surfaces in production if it's not answered in the spec. None of them are complicated to handle once you've defined the expected behavior - but they are expensive to fix after the fact.

---

**Skills:** specification writing, acceptance criteria, edge case analysis, business rule definition, out-of-scope documentation.
