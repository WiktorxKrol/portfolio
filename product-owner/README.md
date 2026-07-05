# Product Owner

---

## E-commerce module in BOWWE - 600 tasks, 1.5 years, live in production

About six months into my time at BOWWE, I looked at our onboarding survey data and saw that around 40% of users who signed up said they came to build an online store. BOWWE at the time was a website builder - no e-commerce existed. Those users were registering, finding out they couldn't do what they came to do, and leaving without paying.

I brought this to the CEO. The e-commerce module was already on the roadmap - but far out. We moved it up. That conversation happened because of the data, not despite it.

I owned the entire scope of the e-commerce module myself. At Ulan, I'm the only person writing specifications - so every one of the 600+ tasks that went into this module was written, estimated, and sequenced by me.

The module covers 9 epics:

- **Store setup** - creating and configuring an online store: name, domain, currency, language, tax settings, shipping rules
- **Products** - product catalogue management: adding products, variants, pricing, inventory, categories, images
- **Cart** - adding products, managing quantities, applying discount codes, calculating totals with tax
- **Payments** - payment gateway integration, transaction processing, handling payment states (pending, completed, failed, refunded)
- **Orders** - order lifecycle management: confirmation, fulfillment status, cancellations, order history for the merchant
- **Customer accounts** - registration, login, order history and tracking from the customer's side
- **Emails** - transactional notifications: order confirmation, shipping update, payment receipt, cancellation
- **Stripe** - payment processing: cards, Apple Pay, Google Pay, webhooks for payment status updates
- **Base.com** - integration with a Polish e-commerce platform for product and order synchronization

Each epic depends on the previous one. The sequence is not arbitrary - it's the order in which the system has to be built.

The hardest part wasn't writing the tasks - it was catching conflicts between them. One example: checkout price display and tax group definitions. One task assumed prices would be shown with tax included or excluded based on a simple country rule. Another task, written separately, defined how tax groups would be configured per product. The two didn't talk to each other - if both went to production as written, users in certain regions would see wrong prices or get an error at payment. I caught it during cross-referencing before it reached a sprint.

I also made scope calls. The clearest one: I cut the invoicing module from the MVP. Users already have invoicing tools they use and trust. Building our own would take real engineering time and produce something they wouldn't switch to. Integrate later, don't compete on day one.

I ran grooming and planning poker sessions with the dev team throughout. I wrote acceptance criteria for every task. I ran UAT sessions with clients before significant releases. I monitored production bugs and prioritized them against feature work each sprint.

---

## Coordinating a three-way integration with TaskRabbit

I was assigned this project. What I got on day one: technical documentation from the furniture retailer with test cases. Everything else came in over time - business model diagrams, meeting notes, follow-up specs.

A large furniture retailer wanted to offer assembly as an add-on at checkout. Customers buy furniture on their platform, TaskRabbit handles the assembly booking. Three systems need to talk to each other. We're the integrator in the middle.

My job was execution, not product thinking. My KPI wasn't coming up with ideas - it was making sure my team delivered on time. And they did, because the work was organized well.

Between meetings I was translating business requirements into sprint scope and functional and non-functional requirements my team could build against. One example: the furniture retailer's system updates order status when furniture ships, but they don't push that information to us. We had to build polling - periodically querying their system to check for updates. That wasn't my idea, it came from the developer. But I made sure it became a properly scoped task with the additional information we needed from the retailer's side to implement it.

On my side: 2 developers, a tester, and a tech lead. On TaskRabbit's side: I worked directly with their Product Owner. On the retailer's side: I worked with their DevOps. The time zone difference was useful - it gave us time to align internally before responding.

---

## Scoping a proptech app - picking up where someone left off

I inherited this project. What I got: incomplete design files and partial requirements. The product is a rental property management app - landlords, tenants, property managers.

The gap I found immediately: everything had been designed from the landlord's perspective. The tenant didn't exist in the designs.

The landlord side had UI designs. The tenant side had nothing. Every flow that landlords initiate has to land somewhere on the tenant's end. One example: the app has a contract generator - landlords can create rental agreements. But there was no flow for how the tenant receives the contract, accesses it, or signs it. The landlord flow ended at "contract generated" with nowhere for that contract to go.

I designed the tenant side of that flow myself - invitation, access, signing - based on competitive benchmarking and business logic. I proposed it to the investor, we discussed it, and it went into the backlog. I did this for several missing flows.

Beyond filling the gaps: ~70 tasks across 12 epics, roughly 570 hours of planned work, sequenced by dependency. 80+ edge cases documented before development started. Legal questions - e-signature validity, deposit limits - routed to external legal counsel instead of written as assumptions.

---

## Owning four products at the same time

At peak I was running four products in parallel. Each one at a different stage, each one needing a different way of working.

**BOWWE** - active e-commerce release, live bugs, hard sprint deadlines. Strict hygiene: clear ownership per bug, no rolling work forward without tracking it.

**Honaro** - UI refresh plus new features. One example: electronic vouchers and a loyalty stamp system - users collect stamps for visits, get rewarded for coming back. CEO's idea, I scoped it from scratch.

**Proptech app** - scoping from scratch, no development yet. One epic scoped and reviewed per session with the investor.

**TaskRabbit integration** - three teams, fixed external deadline. Daily follow-up on every blocking item, visible status across all three teams.

Daily standups on a scoping-phase product waste everyone's time. Epic-by-epic checkpoints on a live release miss bugs. I applied different cadences on purpose because the products needed different things. All four kept moving without any of them going quiet.

---

**Skills:** product scoping, specification writing, backlog ownership, conflict detection, sprint management, UAT, multi-product ownership, cross-company coordination, requirements translation, scope prioritization.
