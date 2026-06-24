# Progress Tracker

A lightweight Scrum board for the course, using the columns from the
2026-05-14 lecture: **To Do → In Progress → Review → Done**. Each item is
written like a Jira issue (Epic / Story / Task) so planning here mirrors the
workflow the course teaches.

_Last updated: 2026-06-24_

## Board

### ✅ Done

| Type | Item | Notes |
| --- | --- | --- |
| Story | Set up course-record repository | README, structure, navigation |
| Task | Take notes — 2026-03-19 workflow lecture | [note](notes/2026-03-19-software-operations-and-workflow.md) |
| Task | Take notes — 2026-05-14 backlog/sprint/Scrum lecture | [note](notes/2026-05-14-jira-backlog-sprint-and-scrum.md) |
| Epic | **Project 0 — Two Sum** | Two C++ impls, GoogleTest, CI, Docker — [repo](https://github.com/charleschiu075/11402_CS351_Project0) |
| Story | Project 0: brute-force `TwoSumArray` (O(n²)) | merged |
| Story | Project 0: hash-map `TwoSumHashTable` (O(n)) | merged |
| Story | Project 0: GitHub Actions CI (build + Docker) | green |
| Epic | **Project B — csvdb** | CSV mini-DB + SQL REPL, C++17 — [repo](https://github.com/charleschiu075/11402_CS351_ProjectB) |
| Story | Project B: tokenizer + recursive-descent parser | merged |
| Story | Project B: executor with index-aware planner | merged |
| Story | Project B: parser tests + benchmark | merged |

### 👀 Review

| Type | Item | Notes |
| --- | --- | --- |
| Task | Cross-link learning log entries to lecture notes | verifying links |

### 🚧 In Progress

| Type | Item | Notes |
| --- | --- | --- |
| Story | Maintain learning log & retrospective | ongoing each session |

### 📋 To Do

| Type | Item | Notes |
| --- | --- | --- |
| Task | Tag a release on each project repo (`v1.0.0`) | practice Git tags + GitHub Releases |
| Task | Write end-of-course retrospective | in [goals-and-review.md](goals-and-review.md) |
| Task | Add a note for the next lecture | when it happens |

## Milestone view

| Milestone | Status | Evidence |
| --- | --- | --- |
| Workflow lecture understood | ✅ Done | [note](notes/2026-03-19-software-operations-and-workflow.md) |
| Scrum/backlog lecture understood | ✅ Done | [note](notes/2026-05-14-jira-backlog-sprint-and-scrum.md) |
| Project 0 built, tested, CI green | ✅ Done | [repo](https://github.com/charleschiu075/11402_CS351_Project0) |
| Project B built, tested | ✅ Done | [repo](https://github.com/charleschiu075/11402_CS351_ProjectB) |
| Releases tagged | 📋 To Do | — |
| Final retrospective | 📋 To Do | [goals-and-review.md](goals-and-review.md) |

## How I keep this current

- Move items left → right as work progresses; re-date the header on each update.
- New work enters **To Do** as a Task under the relevant Story/Epic.
- "Done" requires the work to be *demonstrable* (matches the Scrum definition of
  an increment) — code merged, tests passing, or a note written.
