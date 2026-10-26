# agent-skills

Personal agent skills collection (OpenCode / agents-compatible). Each skill lives in its own subdirectory with a `SKILL.md`.

> ⚠️ The 8 skills form one orchestration chain — `software-dev-orchestrator` dispatches to the other 7. Always install them **side by side in the same skills directory**, not individually.

## Skills

| Skill | Directory | Description |
|---|---|---|
| 软件开发总调度 | [`software-dev-orchestrator/`](./software-dev-orchestrator/) | Full-pipeline orchestrator: spec → design → plan → implement → test cases → review |

## Dispatched skills (used by 软件开发总调度)

| Skill | Phase |
|---|---|
| `spec-driven-development` | 1 Specify / 3 Plan |
| `writing-design-docs` | 2 Design |
| `springboot-patterns` | 4 Implement |
| `java-springboot` | 4 Implement |
| `spring-boot-openapi-documentation` | 4 Implement (API docs) |
| `java-junit` | 4 Tests / 5 Test cases |
| `code-review` | 6 Review |

## Install on another machine

This repo is **private**. Authenticate first (pick one):

- SSH key added to your GitHub account → use the SSH URL below
- `gh auth login` once → HTTPS clone just works
- HTTPS + Personal Access Token (repo read access)

### A. Global install (recommended)

`~/.agents/skills` is auto-discovered by OpenCode (global compatibility source), no config needed.

**Fresh environment** (dir empty or absent) — clone directly into it:

```bash
git clone git@github.com:xpppppppppp/agent-skills.git ~/.agents/skills
```

**Already have `~/.agents/skills` with other skills** — clone elsewhere, copy only the skill directories:

```bash
git clone git@github.com:xpppppppppp/agent-skills.git ~/agent-skills
cp -r ~/agent-skills/*/ ~/.agents/skills/
```

Windows (PowerShell):

```powershell
git clone https://github.com/xpppppppppp/agent-skills.git "$env:USERPROFILE\.agents\skills"
# or if the dir already has content:
git clone https://github.com/xpppppppppp/agent-skills.git "$env:USERPROFILE\agent-skills"
Get-ChildItem "$env:USERPROFILE\agent-skills" -Directory |
  Copy-Item -Destination "$env:USERPROFILE\.agents\skills\" -Recurse
```

### B. Keep the clone separate, register via config

No copying; update with `git pull`.

```bash
git clone git@github.com:xpppppppppp/agent-skills.git ~/agent-skills
```

Add to `~/.config/opencode/opencode.json` (create if missing):

```jsonc
{
  "$schema": "https://opencode.ai/config.json",
  "skills": ["~/agent-skills"]
}
```

### C. Project-only install

```bash
git clone git@github.com:xpppppppppp/agent-skills.git .agents/skills
# or clone elsewhere and copy the 8 skill dirs into .opencode/skills/
```

## Verify

Start `opencode` in any directory and mention `@software-dev-orchestrator` in a prompt — it should load. If a dispatched skill is missing you'll see it fail at that phase.

## Update

```bash
git -C ~/agent-skills pull     # or wherever you cloned it
```
