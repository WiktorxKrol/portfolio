## Turning quantitative UX signals into a prioritized backlog

`⏱️ ~1 min read`

> **🎯 Result:** I built a repeatable process that turns raw UX analytics into clear, scoped tickets, so friction on the website became actionable work instead of a report nobody read.

<details>
<summary><b>🧩 Situation</b> — a UX analytics tool generating signal nobody had a process to act on</summary>

A UX analytics tool (session recording, rage-click, dead-click, and JS-error detection) generated a large amount of signal across a web product, but there was no repeatable way to turn that raw data into engineering work.

</details>

<details>
<summary><b>⚙️ What I did</b> — 2 steps: aggregate by page, work within an API limit</summary>

- Built a process that pulls the tool's metrics through its API, aggregates them by page instead of by raw metric, and generates one clearly-scoped backlog item per problem area — for example, "checkout button unresponsive on mobile, high rage-click rate" instead of a spreadsheet of numbers.
- Worked within a strict daily API limit, so the process had to prioritize which pages to refresh with new data versus rely on cached results.

</details>

**📈 Result.** UX friction became a normal, prioritized part of the backlog and led to actionable insights the team actually used, instead of a report that got ignored.

🏷️ `Data Analysis` `Translating Quantitative Signals into Requirements` `Working Within API Constraints` `Process Design`

---
[← Back to Business Analyst case studies](./README.md)
