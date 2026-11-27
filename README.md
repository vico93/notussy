# Project Kickoff Kit

A portable Agent Skills workflow for project discovery, planning, approval, and implementation handoff. It supports OpenCode and Pi through the standard `SKILL.md` format. The kit stops at handoff; it does not implement the project.

## Install for one project

Copy the `skills/project-kickoff/` directory from this repository into the target project's skill directory. The skill includes its templates and interview guide, so no other repository files are needed.

### OpenCode

Copy to `.opencode/skills/project-kickoff/` in the target project. OpenCode discovers the skill and makes it available to the agent when relevant. To load it directly, mention `@project-kickoff` in your prompt. On OpenCode v2, the skill frontmatter enables `/project-kickoff` in the TUI through `metadata.opencode/slash: "true"`. Availability may differ by version; verify in your installed version.

You can also install it under `.agents/skills/project-kickoff/`, which OpenCode supports and which is also Pi's standard project-level Agent Skills location.

### Pi.dev

Copy to `.agents/skills/project-kickoff/` in the target project. Start Pi from the project or a subdirectory. Pi discovers it and exposes `/skill:project-kickoff` for explicit invocation; it may also load the skill when relevant.

### Copy commands

Run from the target project's root and adjust the source path to your clone. Create the destination parent directory first if needed.

PowerShell:

```powershell
New-Item -ItemType Directory -Force ".opencode\skills" | Out-Null
Copy-Item -Recurse "D:\path\to\notussy\skills\project-kickoff" ".opencode\skills\project-kickoff"

# For Pi.dev or a shared project skill location:
New-Item -ItemType Directory -Force ".agents\skills" | Out-Null
Copy-Item -Recurse "D:\path\to\notussy\skills\project-kickoff" ".agents\skills\project-kickoff"
```

Bash:

```bash
mkdir -p .opencode/skills
cp -R /path/to/notussy/skills/project-kickoff .opencode/skills/

# For Pi.dev or a shared project skill location:
mkdir -p .agents/skills
cp -R /path/to/notussy/skills/project-kickoff .agents/skills/
```

Keep the copied skill in version control if the whole team should use it. To update it, copy the newer `project-kickoff` directory over the project copy after reviewing any local changes.

## What it does

The skill interviews you, confirms its understanding, drafts a development plan in chat, and performs a self-review. It asks for explicit approval before writing `devplan.md` and `handoff.md` to the confirmed target directory. If either file already exists, it asks before replacing anything. It writes documents in the user's language. Verification guidance is planned but not executed during kickoff.

The included interview guide is loaded only when useful. Templates are stored inside the skill at `skills/project-kickoff/templates/` and are available after copying the skill folder. Review the skill before use; after approval, it can create the two kickoff documents in your selected project location.

## Contents

- `skills/project-kickoff/SKILL.md`: shared workflow and boundaries
- `skills/project-kickoff/references/interview.md`: optional interview prompts
- `skills/project-kickoff/templates/devplan.md`: development plan template
- `skills/project-kickoff/templates/handoff.md`: implementation handoff template

No scripts, dependencies, or network access are required.


