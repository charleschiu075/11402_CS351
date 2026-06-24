# 2026-03-19 — Software Operations & the End-to-End Workflow

**Course:** AI-Assisted Software Development · **Instructor:** Yu-Feng Huang, Ph.D.

## Point of view

We looked at the **software operations / software workflow for a mini project**
as a whole, instead of just "writing code." The big takeaway: each tool owns one
stage of the workflow, and they hand off to each other in a predictable order.

## The toolchain and what each tool is *for*

| Stage | Tool | Responsibility |
| --- | --- | --- |
| Project initiation & planning | **Jira** | Define product goal, epics, stories, tasks, sprints |
| Project management & tracking | **Jira** | Backlog, sprint planning, status (To Do → In Progress → In Review → Done) |
| Local development environment | **VSCode** | Write, edit, debug, run; integrated terminal & extensions |
| Version control | **Git** | Branch, commit, pull/merge/rebase, resolve conflicts, track history |
| Remote hosting & collaboration | **GitHub** | Central repo, push, pull requests, review, merge, releases/tags |
| Automated testing & CI | **GitHub Actions** | Run tests, lint, build checks automatically on push/PR |
| Release & versioning | **Git tags + GitHub Releases** | Tag versions, publish release notes & deliverables |

### Roles, restated in one line each

- **Jira** — the *project coordination layer*. It does **not** write code or
  store source. It answers: *What are we building? Who does what? Which sprint?
  What's blocked / in progress / finished?*
- **VSCode** — the *developer workspace*. Where coding actually happens: edit,
  run, debug, view Git changes, connect to GitHub (and sometimes Jira).
- **Git** — the *version control engine*. Manages the history: commit snapshots,
  branches, merges, comparing revisions, recovering old states.
  > Key distinction: **Git is the mechanism; GitHub is the platform.**
- **GitHub** — the *shared remote home* of the code: central repo,
  collaboration, pull requests, code review, releases, and Actions automation.
- **GitHub Actions** — the *automation layer*: test automatically, verify the
  build, check formatting/linting, and **prevent broken code from being merged**.

## End-to-end workflow

The lecture walked through this as one continuous loop:

1. **Start in Jira** — create an Epic for the mini project, break it into
   Stories and Tasks, put tasks into the sprint backlog.
   - *Example:* Epic `Student Score Analyzer` → Story `Import CSV file` →
     Tasks `Implement CSV parser`, `Add error handling`, `Write unit tests`.
2. **Create / connect the GitHub repository** — initialize the repo, add a
   README, `.gitignore`, and project structure. Optionally link Jira issues to
   GitHub (recommended).
3. **Open the project in VSCode** — clone the repo locally; use the editor,
   terminal, and source-control panel.
4. **Develop by task with Git** — for each Jira task: create a branch,
   implement, commit with meaningful messages.
   - *Example:* branch `feature/csv-parser`, commit `Add CSV parsing for
     student records`.
5. **Push to GitHub** — push the branch, open a pull request, reference the Jira
   issue in the PR title/description.
6. **Run GitHub Actions** — tests run automatically; confirm build & test
   status; catch errors *before* merge.
7. **Review and merge** — review the code, revise if needed, merge into `main`
   after checks pass.
8. **Update Jira** — move the issue to Done, track sprint progress, prepare the
   next task.
9. **Release** — create a Git tag (e.g. `v1.0.0`), publish release notes on
   GitHub, optionally attach binaries/reports/docs.

## Pull requests & code review

In real workflows code does **not** go straight from local edit to release.
The path is: `branch → commit → push → pull request → review → merge`.

> Before opening a PR, code should be tested **locally** (manual test) **and
> remotely** (GitHub Actions).

## Scrum (sprint closure & feedback loop)

Software operations isn't only coding — it's iterative management. The Scrum
events that close the loop:

- **Sprint Planning**
- **Daily Scrum**
- **Sprint Review**
- **Retrospective**

## Summary — software operations for a mini project

1. Plan & manage in **Jira** (epic/story/task, backlog, sprints, status).
2. Develop in **VSCode** (write, edit, run, debug locally).
3. Track changes with **Git** (branches, commits, history).
4. Collaborate through **GitHub** (host, push, PRs, review, document).
5. Validate with **GitHub Actions** (automated tests & build checks before merge).
6. Release with **Git tags + GitHub Releases** (stable versions, release notes).

## My takeaways

- I had been thinking of "the repo" as the project; really the project spans
  Jira (plan) + GitHub (code/collab) + Actions (quality gate) + Releases.
- "Git is the mechanism, GitHub is the platform" finally made the branch-vs-PR
  distinction click: branching/committing is Git; PR/review/merge is GitHub.
- The PR quality gate (local test **and** CI) is exactly what Project 0 and
  Project B already do with GitHub Actions — see the [projects](../../projects/).
