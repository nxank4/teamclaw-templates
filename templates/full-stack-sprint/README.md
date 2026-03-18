# Full Stack Sprint Team

Architect, build frontend and backend, QA, and document in one sprint.

## Who is this for?

Development teams and solo developers who want to build a complete feature — from architecture through frontend, backend, testing, and documentation — in a single coordinated sprint.

## Agent Team

| Role | Model | Responsibility |
|------|-------|---------------|
| Architect | claude-sonnet-4-6 | Design systems, define API contracts, keep data models simple |
| Frontend Engineer | claude-sonnet-4-6 | Build clean, accessible UI following the API contract |
| Backend Engineer | claude-sonnet-4-6 | Build reliable APIs and data layers with input validation |
| QA Reviewer | claude-haiku-4-5 | Test integration, error states, and security (happy path + 3 failure scenarios) |
| Documentation Writer | claude-haiku-4-5 | Write API reference, setup instructions, and common gotchas |

## Example Goal

```
Build task management dashboard with frontend and backend for ProjectTracker
```

## Estimated Cost

~$0.18 per run (recommended minimum 2 runs)

## Tips for Best Results

- Start with architecture — the API contract guides both frontend and backend
- The architect defines the contract before engineers start building
- QA tests both integration points and at least 3 failure scenarios
- Documentation activates when "document" or "docs" keywords appear in the goal
- This is the most expensive template — use targeted goals to get the most value
