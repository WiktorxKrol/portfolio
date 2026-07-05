## Building an e-commerce module inside a website builder

> **In one line:** I scoped and delivered 600+ tasks over 1.5 years to add a full e-commerce capability to BOWWE - a drag-and-drop website builder - including store setup, cart, payments, and order management. It's live in production.

**Situation.** BOWWE is a website builder. Users can build landing pages and websites without writing code. The next logical step was e-commerce: let users build and run an online store inside the same tool. No e-commerce existed in the product at all - it had to be built from scratch, alongside ongoing maintenance of the existing product.

**What I did.**

Owned the entire product scope for the e-commerce module from day one:

- Broke the module into epics - store setup, product catalogue, cart and checkout, payment integration, order management, customer accounts, email notifications - and sequenced them by dependency so payment infrastructure was in place before checkout existed.
- Wrote every specification myself. At Ulan, I'm the only person writing specs, so every requirement that reached engineering came through me. Each spec included acceptance criteria, edge cases, and explicit rules for what happens when something goes wrong.
- Ran ongoing grooming and planning poker sessions with the dev team to estimate tasks and keep the backlog realistic.
- Made deliberate scope decisions throughout. The clearest one: I cut the invoicing module from the MVP. Users already have invoicing tools they trust. Building our own would take significant engineering time and produce something users would not switch to. The right call was to integrate with existing tools in a later version - not compete with them on day one.
- Monitored production bugs, prioritized them against feature work, and coordinated fixes with engineers per sprint.
- Ran UAT sessions with clients before each significant release to validate behaviour before it went to all users.
- Presented new e-commerce features to clients in demos.

**Result.** The e-commerce module is live in BOWWE and used in production. The invoicing decision kept the MVP timeline realistic and focused engineering effort on the features that actually drive store creation.

**Skills:** product scoping, backlog ownership, specification writing, sprint management, acceptance criteria, scope prioritization, UAT, stakeholder demos, bug triage.
