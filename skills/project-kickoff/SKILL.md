---
name: project-kickoff
description: Use when the user wants to plan a software project, run a project kickoff, clarify requirements, or prepare a project before coding. Interview, write an approved development plan, and prepare an implementation handoff without implementing the project.
metadata:
  opencode/slash: "true"
---
# Project Kickoff

## Boundary
This workflow ends with an approved `devplan.md` and a useful `handoff.md` in the user-selected target directory. Do not implement the project, modify its source, create scaffolding, install dependencies, or run project-generating commands.

## Workflow

1. **Orient:** Ask about the idea, users and outcome, constraints, existing work, preferred stack/harness, and target directory. Inspect only relevant project context read-only: `README*`, `AGENTS.md`, manifests, and configuration/docs needed to understand the project. Do not read `.env`, credentials, or secret-bearing files. If no target is chosen, suggest `<project-root>/docs/project-kickoff/` and ask the user to confirm or choose another.
2. **Interview:** Follow `references/interview.md` when more discovery is useful. Ask a few related questions at a time. Offer a sensible default when the user is unsure, label it as a proposal, and ask whether to use it. A user may provide an existing plan or ask to skip the interview; preserve supplied decisions, identify gaps, and proceed without forcing redundant questions.
3. **Confirm understanding:** Before drafting, summarize the agreed outcome, scope, constraints, decisions, assumptions, and remaining questions. Invite corrections. Do not proceed on disputed material facts.
4. **Draft in chat:** Use `templates/devplan.md` as the structure, adapting headings to the user's language. Do not write a file yet. Stop asking questions when every section can be completed from user-provided facts or clearly labeled proposals/unknowns; no section should require guessing. Include milestones as a list with dependencies, a “done when” result, and a way to verify each milestone. Perform the self-review checklist below before presenting the draft.
5. **Review and approval:** Present the plan and concise summary. Ask for explicit approval. Incorporate revisions; if material decisions change, ask for approval again. Approval is for this plan and target path.
6. **Write and hand off:** Only after approval, check whether `devplan.md` or `handoff.md` already exists. Never overwrite either silently: ask what to do, or choose a new filename/location with the user's agreement. Save the approved plan with `Status: Approved`, approver (the user's name if provided, otherwise `User`), and approval date filled in. Treat the approved plan as the frozen specification; implementation progress belongs only in `handoff.md`. Create `handoff.md` using `templates/handoff.md`, copying milestones as the initial checklist. Do not implement.
7. **Close:** Confirm paths, approved scope, and remaining questions.

## Self-review before presenting the plan
- Goals have observable outcomes; scope and non-goals are explicit.
- Decisions, assumptions, and open questions are distinguished.
- Milestones are ordered, have dependencies, “done when” outcomes, and verification guidance.
- Risks and constraints are recorded; no commitments were invented.
- The draft and handoff template can be completed without guessing.

## Rules
- Write plan and handoff in the user's language; translate template headings as useful while preserving filenames.
- Do not claim any checks were run. Verification guidance is a plan for future work, not executed validation.
- Keep plan and handoff consistent; mark unknowns explicitly.
- After handoff, do not change milestone state in `devplan.md`; update the single source of progress in `handoff.md` only.
- If unable to write to the confirmed target, provide the approved content in chat instead of writing elsewhere.

