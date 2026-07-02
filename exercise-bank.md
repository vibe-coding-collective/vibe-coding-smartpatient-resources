# Exercise bank — practice in your own world

The session gave you two mini-exercises and a team build. This is everything after: a set of small projects tied to **real jobs at smartpatient**, so you can keep the momentum instead of losing it a week later.

> Part of the 3 July take-home pack. Each exercise leans on a technique from the [field guide](./README.md) — the brief template, the "interview me" pattern, small-step iteration, and the safety basics. Keep it open alongside this one.

## How to use this

- **Solo or in pairs.** Pick one that matches a job you actually do. 30–60 minutes each.
- **Default tool is Figma Make** (everyone has access). Where a tool fits better, it's noted.
- **Levels:** 🟢 start here · 🟡 stretch · 🔴 engineer lane.
- **Use fake data, always.** Every prompt below assumes synthetic or anonymised data. Before you paste anything, run through the [safety notes](./README.md#safety--security-in-your-world). If you want realistic synthetic datasets to practise on, ask us and we'll share some.

---

## Growth & Marketing

### 🟢 App-store performance summariser
- **For:** ASO and User Acquisition
- **The pain:** *"Analyzing app store performance data is the most time-consuming part of my job."*
- **Build:** an app that takes a messy app-store / ASO export (CSV) and returns a one-screen dashboard plus a short "what moved this week and why" readout you could paste into a Monday update.
- **Starter prompt:**
  > Build a dashboard that reads the attached app-store export (downloads, impressions, conversion rate, by country and keyword). Show the week-over-week trend, highlight the three biggest movers, and write a 4-bullet plain-English summary a non-analyst could act on. Data is synthetic.
- **Stretch:** 🟡 have it schedule itself to run every Monday (see Sofiia's scheduling section) and flag only what changed.

### 🟡 Campaign readout + config sanity-checker
- **For:** B2C Growth and App Campaign
- **The pain:** running CleverTap campaigns and then hand-checking configs and click/conversion outcomes.
- **Build:** paste a campaign export → get a plain-English "what changed and why" readout; second mode reads a push / in-app **config** and flags anything risky (broken link, missing deep-link, audience mismatch) before it ships.
- **Starter prompt:**
  > Two tools in one app. (1) Given the attached CleverTap-style campaign export, summarise click and conversion rate by campaign and call out under-performers. (2) Given a push-notification config (title, body, deep link, audience), list anything that looks misconfigured or risky. Synthetic data.
- **Stretch:** a reusable pre-send checklist the whole content team runs.

### 🟡 Pharma competitive-intel daily brief
- **For:** B2B Marketing and leadership
- **The pain:** *"I want market research automated so it tells me every day what's happening in pharma and the competitive landscape, without searching different platforms and manually adding info."*
- **Build:** a research agent that produces a short daily brief on named competitors and pharma topics. This is an **agent/automation** job more than a Make build — a great fit for NotebookLM or a scheduled action from Sofiia's section.
- **Starter prompt:**
  > Act as my pharma market analyst. Each morning, produce a one-page brief on [competitors / topics]: what's new, why it matters to a medication-adherence company, and anything I should act on. Cite sources. Keep it to a 2-minute read.
- **Stretch:** 🔴 wire it to run on a schedule and land in Slack.

---

## Partnerships & Sales

### 🟢 Partner screenshot-approval assembler
- **For:** Partner Success
- **The pain:** *"Our partners need to approve changes in the program with screenshot approval documents. We manually take every screenshot and include it in a document."*
- **Build:** drop in a folder of screenshots plus a short change-log; the tool lays out a clean per-change approval doc (before / after, description, sign-off box) ready to send.
- **Starter prompt:**
  > Build a tool where I upload screenshots and a list of changes, and it generates a partner-approval document: one row per change with before/after images, a plain description, and an approval checkbox. Export-ready. Use the attached brand styling.
- **Stretch:** 🟡 auto-draft the partner-facing cover email that goes with it.

### 🟡 Per-partner update digest ("connect the dots")
- **For:** Partner Success and BD
- **The pain:** *"Connecting dots — checking messages from several sources and formulating a fact-based way forward."*
- **Build:** paste updates from a few sources (email snippets, Slack notes, a status sheet) → get a per-partner status card with "what's new / what's blocked / next touch."
- **Starter prompt:**
  > Given these mixed notes about several partners, produce one status card per partner: current state, what changed this week, blockers, and the single most useful next action. Flag anything time-sensitive. Synthetic notes.
- **Stretch:** rank partners by "needs attention now."

### 🟡 Sales personalisation / proposal-recycler
- **For:** Sales and leadership
- **The pain:** *"Personalising our sales efforts at scale"* and *"recreating presentations and proposals for different customers."*
- **Build:** feed a base proposal plus a synthetic CRM row (contact, company, focus area) → get a tailored draft that keeps your structure but re-frames for that stakeholder.
- **Starter prompt:**
  > Here is our base proposal and a row of details about a pharma stakeholder. Produce a tailored version: same structure and claims, but re-framed for their role, their therapy area, and their stated priorities. Keep it factual — do not invent numbers. Synthetic data.
- **Stretch:** batch it across ten contacts at once.

---

## Product, Insights & Support

### 🟢 Survey open-text theming → chart + slide
- **For:** Insights and Design research
- **The pain:** *"Summarising open-text survey answers, categorising them into themes, and reporting them in a graph in a PPT. ChatGPT isn't reliable for huge data, e.g. 3k replies."*
- **Build:** paste a synthetic export of open-text answers → the tool tags them into themes, counts them, draws a bar chart, and writes a slide-ready summary.
- **Starter prompt:**
  > Take the attached open-text survey answers, cluster them into 6–10 themes, count each, and produce (1) a bar chart of theme frequency and (2) a 5-bullet summary for a slide. Then list any answers that name a specific person so I can remove them. Synthetic data.
- **Why this one matters:** the "flag answers that name a person" step is the safety habit in action — practise it on safe data.

### 🟡 Metric-impact viewer
- **For:** Product Owners
- **The pain:** *"Identifying the effects of the latest app or config changes on metrics like earnings. No change hits one metric only, and keeping the full picture daily is nothing a simple chart can do."*
- **Build:** a small board that shows how one change rippled across several metrics over time (retention, conversion, revenue), with a written "likely story."
- **Starter prompt:**
  > Build a view where I mark a change on a date and see the following two weeks across retention, conversion and revenue side by side, with a short written interpretation of what likely moved and what's noise. Synthetic data.
- **Stretch:** 🔴 connect it to a real (test) data source through an API.

### 🟡 Support "tweak-spotter"
- **For:** User Support
- **The pain:** *"Cases where users shouldn't have to contact us — app flows that need small tweaks. Tweaks that could be done by non-developers who know the app."*
- **Build:** cluster a batch of synthetic support tickets → surface the top flows causing avoidable contacts, and for the top one, draft a small fix as a clean handoff note for engineering.
- **Starter prompt:**
  > Cluster these support tickets by root cause. Show the top 5 avoidable-contact drivers. For the biggest one, write a short spec an engineer could act on: what's confusing, the proposed fix, and how we'd know it worked. Synthetic tickets.
- **Ties to:** the [handoff framework](./README.md#handoffs-from-vibe-coder-to-engineer) — you're producing a route-ready request, not just a complaint.

### 🟡 Acceptance-criteria & priority helper
- **For:** Tech leads / interim POs
- **The pain:** *"Assessing the priority of functionality I'm not familiar with is very time-consuming."*
- **Build:** paste a rough ticket or idea → get drafted acceptance criteria plus a priority rationale you can react to and correct (not accept blindly).
- **Starter prompt:**
  > Given this rough feature idea, draft: (1) clear acceptance criteria in given/when/then form, (2) edge cases we'd otherwise miss, and (3) a first-pass priority with the reasoning, so I can challenge it. Ask me 3 questions first if anything's ambiguous.

---

## Design

### 🟢 Design-system component tester
- **For:** Product & Communication Design
- **The pain:** *"Make alters the very specific screens I share. It doesn't help with testing smaller tweaks with a set design system."*
- **Build:** using the method in **[Keeping Figma Make on your design system](./design-system-with-figma-make.md)**, get Make to output one on-brand MyTherapy component, then test three small variations **without** the whole screen drifting.
- **Starter prompt:**
  > Here is an on-brand screen and our published library. Produce a secondary-style variant of only the primary button. Change nothing else. Then show me two more variants of just that button. Use only library tokens.
- **The lesson:** this is the "80% wall" turned into a controlled loop.

---

## Engineering & QA

### 🔴 Maestro UA-test generator
- **For:** Mobile and QA
- **The pain:** *"We'd like to generate UA tests on Maestro — we have too few tests for regression."*
- **Build:** describe a MyTherapy flow in plain language → generate a Maestro test skeleton, with your conventions captured in an `AGENTS.md` so every future test comes out consistent.
- **Starter prompt:**
  > Given this described user flow (add a medication → set a reminder → confirm it fires), generate a Maestro UA test. Follow the conventions in AGENTS.md. Point out any steps that need a test ID we don't have yet.
- **Ties to:** [rules files](./README.md#set-your-rules-once) — encode the house style once.

### 🔴 Jira ↔ GitHub status view
- **For:** Engineering leadership
- **The pain:** *"Syncing Jira and GitHub task statuses and owners."*
- **Build:** a small dashboard that reconciles a synthetic Jira export against a GitHub export and flags mismatches (done in one, open in the other; no owner).
- **Starter prompt:**
  > Reconcile the attached Jira and GitHub exports by ticket ID. Show a table of mismatches: status conflicts, missing owners, and items in one system but not the other. Synthetic data.
- **Stretch:** connect live via MCP instead of exports (pro-tier — see the field guide).

---

## Ops, HR & Compliance

### 🟢 Sensitive-data-safe helper (People Ops)
- **For:** People Ops / HR
- **The pain:** *"I work almost only with confidential and personal data, and I'm still not sure how to implement AI so it actually saves time."*
- **Build:** a People-Ops helper (e.g. a policy Q&A or a report drafter) that runs entirely on **synthetic** data, with the paste-gate front and centre — the point is to learn the *safe pattern* for sensitive roles.
- **Starter prompt:**
  > Build a policy Q&A tool over the attached (fake) HR handbook. It should answer only from the document, say "not covered" when unsure, and never store or echo personal data. Synthetic content only.
- **The lesson:** for confidential-data roles, the skill is the pattern (anonymise, keep it local, retention off), not the tool.

### 🟡 Compliance doc-review checklist
- **For:** Compliance
- **The pain:** *"Reviewing and updating documents, building reports, assessing apps and services, legal and compliance assessments."*
- **Build:** paste a (fake) policy or vendor doc → get a structured review against a checklist you define, with gaps and suggested edits flagged.
- **Starter prompt:**
  > Review the attached document against this checklist [paste your criteria]. For each item: pass / gap / needs-detail, with the exact line and a suggested fix. Don't invent regulation — flag where I need to verify. Synthetic document.

---

## Turn any of these into a team challenge

For the end-of-session build (cross-functional pairs, mixed levels — don't pair two total beginners), pick one:

- **A — Make sense of the mess:** turn a provided messy synthetic dataset into a decision someone could act on this week (dashboard + short report).
- **B — Partner helper:** the screenshot-approval assembler, or a per-partner update digest (the grind above).
- **C — Growth insight:** channel / campaign performance → plain-English "what changed and why."
- **D — Ship a small MyTherapy-flavoured feature or internal tool** (adherence-streak view, refill-reminder logic tester) with a clean handoff note.
- **E — Insight from noise:** the survey open-text theming tool, presented as one chart + one recommendation.
- **F — The safe one:** any tool built on sensitive-shaped (but synthetic) data that passes the paste-gate cleanly — demo the safety reasoning, not just the app.

Any 🟢 or 🟡 exercise above also works as a 45-minute challenge. The demo matters as much as the build: presenting your work to the room is the same communication skill, pointed at people instead of at the AI.
