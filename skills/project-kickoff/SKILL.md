---
name: project-kickoff
description: Interview the user about a proposed software project, create an actionable development plan, obtain approval, and prepare a handoff without implementing the project.
---

# Project Kickoff

## Boundary
Your job ends with an approved `devplan.md` and a useful `handoff.md` in the user-selected target directory. Do not implement the project, modify its source, create scaffolding, install dependencies, or run project-generating commands. If asked to begin implementation, explain that this workflow ends at handoff.

## Workflow
1. **Orient:** Ask about the idea, intended users and outcome, constraints, preferred stack/harness, target directory, and existing work. Ask a few related questions at a time. Inspect existing files read-only when available.
2. **Pre-interview:** Clarify problem, scope, non-goals, key journeys, acceptance criteria, technical constraints, risks, and unresolved decisions. Distinguish facts, assumptions, and open questions. Do not invent commitments.
3. **Draft:** Create `devplan.md` from `templates/devplan.md`. Include goals, scope, approach, milestones, criteria, risks, and open questions. Validation is optional and framed as a proposal unless requested.
4. **Review and approval:** Present a concise summary and plan. Obtain explicit approval before writing deliverables into the target directory. Incorporate revisions and seek approval again if material decisions change.
5. **Handoff:** After approval, save `devplan.md` and create `handoff.md` from `templates/handoff.md`. State where a future agent should start, approved scope, constraints, open questions, and reporting expectations. Do not implement.
6. **Close:** Confirm paths and summarize approved scope and remaining questions.

## Quality
- Never write to the target until it is identified and the plan is explicitly approved.
- Mark unknowns; keep plan and handoff consistent.
- Do not claim validation was run unless it was.
- If unable to write the selected directory, provide artifacts instead of choosing another location.

## Optional validation checklist
- Goals have observable acceptance criteria.
- Scope and non-goals are explicit.
- Decisions, assumptions, and questions are distinguishable.
- Milestones are ordered and reviewable.
- Handoff points to the plan and names the first step without doing it.
