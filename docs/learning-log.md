# Learning Log

A running, dated log of what I actually learned each session — concepts,
"aha" moments, and things I still want to follow up on. Newest entries on top.

Format per entry: **what I learned**, **how I applied it**, **open questions**.

---

## 2026-05-14 — Backlog, sprint, and Scrum artifacts

**Learned**
- The Scrum loop: `Product Backlog → Sprint Planning → Sprint Backlog →
  Increment`, and that the point is repeated useful increments, not one big
  delivery.
- Clear distinction between **Product Backlog** (everything we *might* do) and
  **Sprint Backlog** (what we *commit to now*).
- Jira issue hierarchy **Epic → Story → Task**, and writing stories in the
  "As a … I want … " voice.
- Where AI fits: it can draft Epics/Stories/Tasks and test-case ideas, but I
  own sizing, sprint goals, and *explaining why* each task matters.

**Applied**
- Re-read my Project B history and saw it already follows Epic→Story→Task
  (parser/tokenizer/executor as stories; individual features as tasks).
- Reframed my [progress tracker](progress-tracker.md) board into the
  `To Do → In Progress → Review → Done` columns from the slides.

**Open questions**
- How granular should a Task be before it's "too large"? Rule of thumb?
- Best practice for linking a Jira issue key to a GitHub branch/PR name.

→ Full notes: [`notes/2026-05-14-jira-backlog-sprint-and-scrum.md`](notes/2026-05-14-jira-backlog-sprint-and-scrum.md)

---

## 2026-03-19 — The end-to-end software workflow

**Learned**
- Each tool owns one stage and hands off to the next:
  Jira (plan) → VSCode (develop) → Git (version) → GitHub (collaborate) →
  GitHub Actions (validate) → Git tags + Releases (ship).
- The line that stuck: **"Git is the mechanism; GitHub is the platform."**
- The PR path `branch → commit → push → PR → review → merge`, and that code
  should be tested **locally and in CI** *before* the PR is merged.

**Applied**
- Audited Project 0 and Project B: both already use a GitHub Actions workflow
  as the pre-merge quality gate, which is exactly the "validate before merge"
  step from the lecture.
- Started committing in smaller, task-sized chunks with meaningful messages
  instead of one big commit at the end.

**Open questions**
- When is a release tag (`v1.0.0`) warranted for a course-sized project?
- How much of the Jira ↔ GitHub linking is worth setting up for a solo project?

→ Full notes: [`notes/2026-03-19-software-operations-and-workflow.md`](notes/2026-03-19-software-operations-and-workflow.md)

---

## How I use this log

- One entry per class (or per significant work session).
- I write it the same day while it's fresh, then revisit during the
  [retrospective](goals-and-review.md) to spot patterns.
