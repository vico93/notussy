# Project Kickoff Kit

A portable Agent Skills workflow for turning an early project idea into an approved plan and a clear handoff. It supports OpenCode and Pi with one shared skill. The kit conducts discovery, planning, approval, and handoff only; it does not implement the project.

## Install for one project

Copy the `project-kickoff` skill folder from this repository into the target project's supported skills directory. Keep the folder name and `SKILL.md` together. No global installation is needed.

### OpenCode

From the target project root, copy:

```text
notussy/skills/project-kickoff/
    -> <target-project>/.opencode/skills/project-kickoff/
```

The resulting file should be `.opencode/skills/project-kickoff/SKILL.md`. OpenCode discovers project skills there. In a session, invoke it as `/project-kickoff` or ask the agent to use the `project-kickoff` skill.

Alternatively, OpenCode also discovers `.agents/skills/`; use `.agents/skills/project-kickoff/` if you want the same project skill location to work across compatible harnesses.

### Pi.dev

Copy the same folder to:

```text
notussy/skills/project-kickoff/
    -> <target-project>/.agents/skills/project-kickoff/
```

Pi discovers project skills under `.agents/skills/`. Start Pi from the project (or a subdirectory) and invoke `/skill:project-kickoff`, or ask Pi to use that skill.

### Copy commands

Run from the target project's root, adjusting the source path to your clone:

```powershell
# OpenCode
Copy-Item -Recurse "D:\path\to\notussy\skills\project-kickoff" ".opencode\skills\project-kickoff"

# Pi.dev (portable Agent Skills location)
Copy-Item -Recurse "D:\path\to\notussy\skills\project-kickoff" ".agents\skills\project-kickoff"
```

Create the destination parent directory first if it does not exist. Alternatively, copy the folder in your file manager. Keep the skill in version control if the whole team should use it.

## Use the kit

The skill interviews you, drafts `devplan.md`, presents it for explicit approval, then prepares `handoff.md`. It writes those two documents into the target directory you choose only after approval. Validation is optional. Templates are in `templates/` for reference or customization.

For OpenCode, `adapters/opencode/command/project-kickoff.md` is an optional command entry point; the shared skill is sufficient for installation and use. Pi uses the standard skill command directly.

The workflow stops at handoff. It does not implement the project. Review the skill and templates before using them; the instructions may create files after you approve the plan.

## Contents

- `skills/project-kickoff/SKILL.md`: shared workflow and boundaries
- `adapters/`: harness-specific entry points
- `templates/devplan.md`: development plan template
- `templates/handoff.md`: implementation handoff template

Validation is optional. No scripts, dependencies, or network access are required.
