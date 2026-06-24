# 11402 CS351 — AI-Assisted Software Development

> Yuan Ze University (YZU), Department of Computer Science & Engineering
> Course: **AI-Assisted Software Development** · Term **11402** (Spring, AY 114)
> Instructor: Yu-Feng Huang, Ph.D.

This repository is my **personal course record and learning portfolio** for
CS351. It is not a single program — it is the place where I keep track of *how*
I work, what I learn each week, and how the two course projects fit into the
end-to-end software workflow the course teaches.

The course is built around one core idea from the lectures:

> **Software development is not only coding.** It is a workflow — plan, develop,
> review, automate, release — managed iteratively with Agile/Scrum, and
> increasingly *assisted* (not replaced) by AI.

## Purpose

The goals of keeping this repository are to:

1. **Practice the full software operations workflow** for a mini project:
   `Jira → VSCode → Git → GitHub → GitHub Actions → Release`.
2. **Document my learning** through dated notes, a running learning log, and a
   progress tracker so the *process* is visible, not just the final code.
3. **Connect theory to practice** by linking each concept (backlog, sprint,
   PR, CI, release) to the two real projects I built during the course.
4. **Reflect** on goals at the start and review outcomes at the end of each
   phase, the way a Scrum team runs sprint reviews and retrospectives.

## Prerequisites

| Area | What you should have | Used for |
| --- | --- | --- |
| Command line | Basic shell navigation | Running builds, git |
| Git & GitHub | An account + Git installed | Version control, PRs, releases |
| Editor | VSCode (recommended) | Local development workspace |
| C++ toolchain | A C++17 compiler + CMake ≥ 3.16 | Building the course projects |
| Containers | Docker (optional) | Reproducible build for Project 0 |
| Planning | A Jira (or equivalent) account | Epics, stories, backlog, sprints |
| Foundations | Basic data structures & algorithms | Project logic (Two Sum, CSV DB) |

## Setup

```bash
# 1. Clone this course-record repository
git clone https://github.com/charleschiu075/11402_CS351.git
cd 11402_CS351

# 2. (Optional) clone the two project repositories alongside it
git clone https://github.com/charleschiu075/11402_CS351_Project0.git
git clone https://github.com/charleschiu075/11402_CS351_ProjectB.git
```

Everything in *this* repo is Markdown — no build step is required to read it.
Build and run instructions for the actual code live in each project's own
repository (linked below).

## Navigation

| Section | What's inside |
| --- | --- |
| [`docs/progress-tracker.md`](docs/progress-tracker.md) | Sprint-style board of what's To Do / In Progress / Review / Done |
| [`docs/learning-log.md`](docs/learning-log.md) | Dated, running log of what I learned each session |
| [`docs/notes/`](docs/notes/) | Lecture notes, one file per class |
| [`docs/goals-and-review.md`](docs/goals-and-review.md) | Goals set up front + sprint review / retrospective |
| [`projects/`](projects/) | Overview of and links to Project 0 and Project B |

## Repository layout

```
11402_CS351/
├── README.md                  # you are here
├── docs/
│   ├── progress-tracker.md     # Scrum-style board
│   ├── learning-log.md         # dated learning entries
│   ├── goals-and-review.md     # goals, sprint reviews, retrospectives
│   └── notes/                  # one note file per lecture
└── projects/
    └── README.md               # links + summaries for Project 0 and Project B
```

## Related repositories

- **Project 0 — Two Sum:** https://github.com/charleschiu075/11402_CS351_Project0
- **Project B — csvdb (CSV mini-database):** https://github.com/charleschiu075/11402_CS351_ProjectB

---

*This is a learning portfolio. Notes are written in my own words from class;
project repositories contain the runnable code.*
