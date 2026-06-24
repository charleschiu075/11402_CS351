---
marp: true
title: "CS351 Final Presentation — From Code to Workflow"
author: "Charles Chiu"
theme: default
paginate: true
---

<!--
Final presentation deck for CS351 (AI-Assisted Software Development).

How to render:
  - Quickest: open in VS Code with the "Marp for VS Code" extension, then run
    "Marp: Export Slide Deck" to produce PDF / PPTX / HTML.
  - CLI: npx @marp-team/marp-cli docs/final-presentation.md -o slides.pdf
         npx @marp-team/marp-cli docs/final-presentation.md -o slides.pptx

Text inside these HTML comments is a Marp presenter note (visible in presenter
mode, hidden on the slide). The blue circle marks a live-demo cue.

Notes: Open on the thesis. Everything in the next ~12 minutes is evidence for
this one sentence. Four repositories, one workflow.
-->

<!-- _class: lead -->
<!-- _paginate: false -->

# From Code to Workflow

## CS351 — AI-Assisted Software Development

**Charles Chiu** · YZU CSE · Term 11402
Instructor: Yu-Feng Huang, Ph.D.

> "Software development is not only coding. It is a workflow —
> plan → develop → review → automate → release —
> *assisted, not replaced,* by AI."

---

# Four repositories, one workflow

`Jira → VSCode → Git → GitHub → GitHub Actions → Release`

| Repository | Role in the story |
| --- | --- |
| `charleschiu075.github.io` | Personal website / portfolio |
| `11402_CS351` | Course record & learning log |
| `11402_CS351_Project0` | Two Sum — algorithm + CI + Docker |
| `11402_CS351_ProjectB` | csvdb — CSV mini-database |

<!--
Notes: Two are "engineering" projects, two are "portfolio/process". Together
they show the full plan-to-ship workflow, not just code.
-->

---

# 1 · Personal Website

**Live:** https://charleschiu075.github.io · **Repo:** `charleschiu075.github.io`
**Tech:** buildless — pure HTML + CSS + vanilla JS on GitHub Pages (no framework, no build step)

**Design concept**

- Multi-section portfolio; dark/light theme — system detection + manual toggle + `localStorage`, set **before paint** (no flicker)
- **Data-driven**: add a project = add one JS object, no HTML edits
- Responsive `clamp()` type · scroll-reveal (Intersection Observer) · custom `404`
- SEO + a11y: Open Graph, JSON-LD `Person`, ARIA, skip link

**Future:** blog section · auto-pull projects from the GitHub API · contact form

🔵 *Demo: toggle dark / light live*

<!--
Notes: Emphasise "buildless" and "data-driven" — design decisions, not just
features. The one-object-per-project trick is the highlight.
-->

---

# 2 · Course Repository — a learning portfolio

`11402_CS351` — **not a program; a record of *how* I work.**

- `docs/progress-tracker.md` — Scrum board: To Do / In Progress / Review / Done
- `docs/learning-log.md` — dated entries · `docs/notes/` — one file per lecture
- `docs/goals-and-review.md` — goals + sprint review + retrospective

**Two lessons that stuck**

- *"Git is the mechanism; GitHub is the platform."*
- Scrum: Product Backlog → Sprint → Increment; Epic → Story → Task
- Retro (honest): the hardest part was judging task size — some "tasks" were really stories.

<!--
Notes: This repo is the "process" evidence. Point out the retrospective —
showing you reflected, not just coded, is what the course rewards.
-->

---

# 3 · Project 0 — Two Sum (goal & algorithms)

**Goal:** use LeetCode #1 as a vehicle for the *whole* workflow —
two implementations, unit tests, CI, and Docker packaging.

| Function | Approach | Time | Space |
| --- | --- | --- | --- |
| `TwoSumArray` | brute-force nested loop | O(n²) | O(1) |
| `TwoSumHashTable` | single-pass hash map (store complement) | O(n) avg | O(n) |

Jira-driven history (`KAN` key): `Planning → KAN-9-two-sum-array → KAN-10-two-sum-hash`

<!--
Notes: The algorithm is deliberately simple — the point is the engineering
around it. The hash version trades O(n) space for O(n) time.
-->

---

# 3 · Project 0 — testing & CI highlight

- **GoogleTest, parametrized over both implementations → 28 tests (14 cases × 2)**
- CI runs on **every push / PR** with two jobs:
  1. Native Ubuntu build + `ctest`
  2. Multi-stage **Docker** build that runs `ctest` *inside* the builder stage
- **Highlight:** one test suite proves both algorithms agree; CI + Docker = a reproducible pre-merge quality gate (the build fails if any test fails).

🔵 *Demo: show green CI checks on a PR; run `./build/two_sum`*

<!--
Notes: "28 tests = 14 cases × 2 impls" is the memorable number. Stress that
the Docker image itself runs the tests — you cannot ship a broken build.
-->

---

# 4 · Project B — csvdb (goal & functions)

In-memory CSV mini-database with a SQL-subset REPL. **C++17, STL only.**

- **REPL:** `.load`, `.tables`, `.schema`, `.mode table|csv`, `.help/.exit`
- **SQL:** `SELECT … FROM … WHERE …`, `CREATE INDEX ON t(col)`
- **Predicates:** `= != <> < <= > >=`, `IS [NOT] NULL`, `AND` / `OR`, parentheses

<!--
Notes: Frame it as "a tiny SQLite". STL-only is a real constraint worth naming.
-->

---

# 4 · Project B — technical highlights

**Pipeline:** Tokenizer → recursive-descent Parser → RFC 4180 CsvLoader →
Database (hash indices) → index-aware Executor → Formatter

- **Predicate binding:** resolve each column once, cache `col_idx` →
  turns *N×k* hash lookups into *k* on an *N*-row scan
- **Index planner:** flat top-level `AND` → probe a hash index on an equality
  conjunct → filter the rest; any other shape falls back to a full scan
- **Honest design:** string-only values (lexicographic compare), explicit NULL
  semantics, documented extension points (typed columns, range index, JOIN, persistence)

<!--
Notes: Predicate binding is the strongest engineering story — a measurable
optimization with a written rationale (it shipped as its own PR). Don't hide
the limitations; naming them shows judgment.
-->

---

# 4 · Project B — live demo

```sql
.load people.csv people
.schema people
SELECT name, dept FROM people WHERE dept = 'Eng' AND active = '1';
CREATE INDEX ON people(dept);   -- rerun the query: the planner probes the index
.mode csv
```

🔵 *Centerpiece demo — narrate the planner before vs. after the index*

<!--
Notes: This is the most impressive live moment. Run the query once (full scan),
create the index, run again and explain the planner now probes it. Record a
screencast as a backup in case the live run fails.
-->

---

# 5 · GitHub workflow evidence

| Repo | Branch style | PRs | Merges |
| --- | --- | --- | --- |
| Project 0 | `KAN-9/10-*` (Jira) | 4 | 3 merged, 1 closed-unmerged |
| Project B | `NL1142-4-*`, `claude/*` | 2 | 2 |
| Course | `claude/*` | 1 | 1 |
| Website | `claude/*` | 1 | 1 |

- Every change followed `branch → PR → CI → merge`; **two Jira keys** (`KAN`, `NL`) link issues to branch names.
- Solo project → PR bodies + CI **are** the review record. One PR closed unmerged = real branch housekeeping, not rubber-stamping.

<!--
Notes: The closed-unmerged PR is a feature, not a flaw — it shows not every
branch ships as-is. The Jira-key branch naming answers an open question from
my own learning log.
-->

---

# 6 · AI-Assisted Development

**Used (with proof):** Claude Code drove the site redesign, the course docs, and
Project B's WHERE-binding optimization — visible as `claude/*` branches with
session links in the PR bodies.

- **AI helped:** scaffolding, documentation, an optimization pass, test-case ideas, backlog breakdown
- **I verified:** correctness via tests/CI, task sizing, the *why*, design trade-offs
- **Learned:** keep AI work on its own branch + PR so it's reviewable like any change; CI is the objective check on AI output

> "AI assists, but the student owns the understanding."

<!--
Notes: Be concrete about the division of labour: AI drafts, the human owns
verification and architecture. The claude/* PRs are your evidence.
-->

---

<!-- _class: lead -->

# Closing

Four repositories → one end-to-end, **AI-assisted** workflow.

**Honest next steps:** tag `v1.0.0` + release notes · write the end-of-course
retrospective · formalize Jira ↔ GitHub linking

### Thank you — questions?

https://charleschiu075.github.io

<!--
Notes: Close by returning to the thesis. The "honest next steps" come straight
from goals-and-review.md — showing you know what's unfinished is a strength.
-->
