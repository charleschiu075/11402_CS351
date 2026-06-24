# Goals & Review

Goals set at the start, and reviews/retrospectives written as the course
progresses — modeled on the Scrum **Sprint Review** (what got done) and
**Retrospective** (how the process went) from the 2026-05-14 lecture.

## Course goals

By the end of the course I want to be able to:

1. **Run the full workflow end to end** for a mini project, unaided —
   `Jira → VSCode → Git → GitHub → GitHub Actions → Release`.
2. **Explain, not just perform** each step (the lecture's rule: AI can assist,
   but I own the understanding).
3. **Decompose work** with the Epic → Story → Task hierarchy and plan a
   realistic sprint.
4. **Use CI as a real quality gate** — nothing merges to `main` until tests
   pass locally *and* in GitHub Actions.
5. **Ship versioned releases** with Git tags and GitHub Release notes.

### How I'll measure each goal

| Goal | Definition of done |
| --- | --- |
| Full workflow | Both projects went plan → code → PR → CI → merge |
| Explain each step | Notes + learning log written in my own words |
| Decomposition | Project B split into subsystem stories/tasks |
| CI quality gate | `ci.yml` green on every merged PR |
| Versioned releases | `v1.0.0` tag + release notes on each project repo |

---

## Sprint review — mid-course (as of 2026-06-24)

**What's done / demonstrable**
- Two projects built, tested, and merged with passing CI:
  [Project 0](https://github.com/charleschiu075/11402_CS351_Project0) (Two Sum,
  native + Docker CI) and
  [Project B](https://github.com/charleschiu075/11402_CS351_ProjectB)
  (csvdb, parser + executor + tests).
- Lecture notes and a learning log captured for both lectures so far.
- This course-record repository set up with a tracked board.

**Not done yet**
- No tagged releases / GitHub Release notes on the project repos.
- Jira ↔ GitHub issue linking not formally set up (solo project, lower priority).

## Retrospective — mid-course

| Prompt | Reflection |
| --- | --- |
| **What went well** | Branch-per-task + CI gate caught bugs before merge; smaller commits made history readable. |
| **What was hard** | Judging task size — some "tasks" were really stories and grew mid-sprint. |
| **What I'll change** | Split work smaller up front; write the sprint goal *before* coding, not after. |
| **Where AI helped** | Drafting test-case ideas and story breakdowns; I kept ownership of sizing and the "why." |

## Action items for the rest of the course

- [ ] Tag `v1.0.0` and write release notes for Project 0 and Project B.
- [ ] Practice writing a sprint goal before starting the next task.
- [ ] Keep the [progress tracker](progress-tracker.md) and
      [learning log](learning-log.md) updated each session.
- [ ] Write a final end-of-course retrospective here.

---

## End-of-course retrospective

_To be written at the end of the term — will revisit each goal above, mark it
met / partially met / missed, and capture the single biggest lesson from the
course._
