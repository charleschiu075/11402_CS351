# 2026-05-14 — Jira Backlog, Sprint, and Scrum

**Course:** AI-Assisted Software Development · **Topic:** Planning software work
with Agile artifacts, sprint goals, and Jira boards.

The flow we kept coming back to:

```
Product Backlog  →  Sprint Planning  →  Sprint Backlog  →  Increment
(all possible work)  (choose focus)     (this sprint)      (usable result)
```

## Learning objectives (from the slides)

- Understand the basic idea of Scrum.
- Explain the relationship among Scrum, backlog, sprint, and Jira.
- Distinguish **Product Backlog** from **Sprint Backlog**.
- Create Jira issues: **Epic**, **Story**, **Task**.
- Move selected backlog items into a sprint and track progress.

## What is Scrum?

An **Agile framework** for managing software development through short,
inspectable cycles. Three moves repeat:

1. **Break down work** — large goals become smaller, discussable, implementable items.
2. **Plan short cycles** — the team selects *realistic* work for a fixed sprint.
3. **Review and improve** — review outcomes, reflect on process improvements.

> Core idea: **don't finish the whole project at once — deliver useful
> increments repeatedly.**

## Scrum roles (course version)

| Role | Real responsibility | In this course |
| --- | --- | --- |
| **Product Owner** | Defines goals and priorities | Student/instructor clarifies requirements |
| **Scrum Master** | Helps the team follow Scrum, removes blockers | Team leader / rotating student role |
| **Developers** | Build, test, document the product | Students implementing the project |

> For an individual project, one student may play all roles in a simplified way.

## Scrum artifacts

| Artifact | Question it answers | Meaning |
| --- | --- | --- |
| **Product Backlog** | "What may need doing *eventually*?" | All possible work items |
| **Sprint Backlog** | "What will we complete *now*?" | Items selected for the current sprint |
| **Increment** | "What can we *demonstrate*?" | The completed, usable result of a sprint |

*Example — Student Grade Calculator:* backlog items `Input scores`,
`Calculate average`, `Assign letter grade`, `Write basic unit tests` →
Increment: a basic calculator that takes scores and shows final grades.

## Scrum events

1. **Sprint Planning** — choose tasks from the backlog.
2. **Daily Scrum** — briefly report progress and blockers.
3. **Sprint Review** — show the working result / project update.
4. **Retrospective** — reflect on process and improvement.

> Course simplification: these can happen in class, online, or as a short
> written reflection.

## Relationship: Scrum, Backlog, Sprint, Jira

```
Project Goal
   → Product Backlog            (ordered list of work items)
      → Sprint Planning
         → Sprint Backlog        (the short development cycle's work)
            → Development Sprint
               → Review + Reflection
```

- **Scrum** = the project-management *framework*.
- **Backlog** = the *ordered list* of work items.
- **Sprint** = the short development *cycle*.
- **Jira** = the *tool* used to manage all of the above.

## Jira issue hierarchy

```
Epic    Student Grade Calculator
 └─ Story   Score Input
     ├─ Task   Define input format
     └─ Task   Validate score range
```

*Example stories (user-story voice):*
- "As a teacher, I want to enter student scores."
- "As a teacher, I want the system to calculate average scores."
- "As a student, I want to see my final letter grade."

## In-class activity — Student Grade Calculator

Goal: build a simple calculator that computes and displays final grades.

1. Accept student name and scores.
2. Calculate total and average score.
3. Convert the average into a letter grade.
4. Display the result.
5. Include simple test cases.

### Student practice workflow

`Define Scrum project goal → Create Epic → Create User Stories → Create Tasks →
Create Product Backlog → Plan Sprint 1 → Track progress on board`

**Board columns:** `To Do → In Progress → Review → Done`
(this is exactly the structure I use in [`progress-tracker.md`](../progress-tracker.md).)

## AI-assisted development connection

| AI can help with | The student is responsible for |
| --- | --- |
| Breaking requirements into Epics/Stories/Tasks | Checking whether tasks are too large |
| Improving story descriptions | Writing realistic sprint goals |
| Generating test-case ideas | Explaining *why* each task matters |

> **Important:** AI *supports* planning, but the student must understand and be
> able to *explain* the workflow. AI assists; it does not replace judgment.

## My takeaways

- Product Backlog vs Sprint Backlog finally clicked: backlog = *everything we
  might do*; sprint backlog = *the slice we commit to now*.
- The Epic → Story → Task hierarchy maps cleanly onto how I split Project B
  (parser → tokenizer/parser/executor as stories, individual features as tasks).
- The "AI can help / student decides" split is the whole point of the course:
  use AI to draft and accelerate, but own the understanding.
