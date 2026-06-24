# Projects

The runnable code for the course lives in two separate repositories. This page
summarizes each one and maps it back to the workflow concepts from the
[lecture notes](../docs/notes/). The projects are where the
`plan → develop → review → automate → release` cycle was actually practiced.

| Project | What it is | Language | CI | Repository |
| --- | --- | --- | --- | --- |
| **Project 0** | Two Sum (LeetCode #1), two implementations | C++17 | GitHub Actions | [11402_CS351_Project0](https://github.com/charleschiu075/11402_CS351_Project0) |
| **Project B** | `csvdb` — in-memory CSV mini-database + SQL REPL | C++17 | GitHub Actions / CTest | [11402_CS351_ProjectB](https://github.com/charleschiu075/11402_CS351_ProjectB) |

---

## Project 0 — Two Sum

A focused warm-up that exercises the full workflow on a small, well-understood
problem: two implementations of LeetCode #1, with tests, CI, and Docker.

| Function | Approach | Time | Space |
| --- | --- | --- | --- |
| `TwoSumArray` | Brute-force nested loop | O(n²) | O(1) |
| `TwoSumHashTable` | Single-pass hash map | O(n) avg | O(n) |

- **Tests:** GoogleTest, parametrized across both implementations.
- **CI:** GitHub Actions runs a native build + `ctest`, and a multi-stage
  Docker build that runs the suite inside the builder stage.
- **Workflow practice:** branch-per-task, PRs, and a green CI gate before merge —
  the "validate before merge" step from the 2026-03-19 lecture.

**Repository:** https://github.com/charleschiu075/11402_CS351_Project0

## Project B — csvdb

A larger project: a minimal in-memory CSV database with a SQL-subset REPL
(C++17, STL only). This is where the Epic → Story → Task decomposition from the
2026-05-14 lecture paid off, because the system splits cleanly into stages.

```
Tokenizer  -> Token[]        state machine over characters
Parser     -> Statement AST  recursive descent (OR < AND < primary)
CsvLoader  -> CsvData        RFC 4180 state machine
Database   -> Tables         in-memory, hash-based indices
Executor   -> ResultSet      index-aware planner for top-level AND chains
Formatter  -> stdout         aligned table or CSV output
```

- **Supports:** `SELECT … FROM … [WHERE …]`, `CREATE INDEX`, comparison/`IS NULL`
  predicates combined with `AND`/`OR`/parentheses.
- **Tests:** parser tests, a functional demo, and an index-vs-full-scan benchmark.
- **Workflow practice:** each subsystem (tokenizer, parser, executor) was a Story;
  individual features and fixes were Tasks — mirroring the Jira hierarchy.

**Repository:** https://github.com/charleschiu075/11402_CS351_ProjectB

---

## How the projects map to the course concepts

| Course concept (lecture) | Where it shows up |
| --- | --- |
| Epic / Story / Task decomposition | Project B subsystems as stories |
| Branch per task, meaningful commits | Both repos' Git history |
| Pull request + review before merge | Both repos' merged PRs |
| GitHub Actions as the quality gate | `.github/workflows/ci.yml` in both repos |
| Test locally **and** in CI before merge | Project 0 (Docker + native) |
| Release & versioning (Git tags) | Planned — see [progress tracker](../docs/progress-tracker.md) |
