## E-commerce module in BOWWE - 600 tasks, 1.5 years, live in production

About six months into my time at BOWWE, I looked at our onboarding survey data and saw that around 40% of users who signed up said they came to build an online store. BOWWE at the time was a website builder - no e-commerce existed. Those users were registering, finding out they couldn't do what they came to do, and leaving without paying.

I brought this to the CEO. The e-commerce module was already on the roadmap - but far out. We moved it up. That conversation happened because of the data, not despite it.

---

**What I actually did for 1.5 years.**

I owned the entire scope of the e-commerce module myself. At Ulan, I'm the only person writing specifications - so every one of the 600+ tasks that went into this module was written, estimated, and sequenced by me.

The module covers 7 epics:

- **Store setup** - creating and configuring an online store: name, domain, currency, language, tax settings, shipping rules
- **Products** - product catalogue management: adding products, variants, pricing, inventory, categories, images
- **Cart** - adding products, managing quantities, applying discount codes, calculating totals with tax
- **Payments** - payment gateway integration, transaction processing, handling payment states (pending, completed, failed, refunded)
- **Orders** - order lifecycle management: confirmation, fulfillment status, cancellations, order history for the merchant
- **Customer accounts** - registration, login, order history and tracking from the customer's side
- **Emails** - transactional notifications: order confirmation, shipping update, payment receipt, cancellation
- **Stripe** - payment processing integration: cards, Apple Pay, Google Pay, webhooks for payment status updates
- **Base.com** - integration with a Polish e-commerce platform for product and order synchronization

Each epic depends on the previous one. Payments can't exist before cart. Cart can't exist before products. The sequence is not arbitrary - it's the order in which the system has to be built.

The hardest part wasn't writing the tasks - it was catching conflicts between them. E-commerce has to have consistent logic across the entire flow, and when you're writing 600 tasks across multiple epics over many months, inconsistencies hide.

The one that comes to mind: checkout price display and tax group definitions. One task assumed prices would be shown with tax included or excluded based on a simple country rule. Another task, written separately, defined how tax groups would be configured per product. The two didn't talk to each other - if both went to production as written, users in certain regions would see wrong prices or get an error at payment. I caught it during cross-referencing before it reached a sprint.

I also made scope calls throughout. The clearest one: I cut the invoicing module from the MVP. Users already have invoicing tools they use and trust. Building our own would take real engineering time and produce something they wouldn't switch to. I documented the decision and the reasoning - integrate later, don't compete with tools users already rely on.

---

**The numbers.**

600+ tasks. 12 epics. 1.5 years. Live in production.

I ran grooming and planning poker sessions with the dev team throughout. I wrote acceptance criteria for every task. I ran UAT sessions with clients before significant releases. I monitored production bugs and prioritized them against feature work each sprint.

---

**Skills:** product scoping, specification writing, conflict detection across large backlogs, acceptance criteria, sprint management, UAT, scope prioritization, bug triage.
