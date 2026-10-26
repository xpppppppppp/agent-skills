# agent-skills

Personal agent skills collection (OpenCode / agents-compatible). Each skill lives in its own subdirectory with a `SKILL.md`.

## Skills

| Skill | Directory | Description |
|---|---|---|
| 软件开发总调度 | [`software-dev-orchestrator/`](./software-dev-orchestrator/) | Full-pipeline orchestrator: spec → design → plan → implement → test cases → review, dispatching to specialized skills with human gates between phases. |

## Usage

Sync a skill directory into `.agents/skills/` (global: `~/.agents/skills/`, per-project: `<repo>/.agents/skills/`).

```bash
# clone private repo
git clone git@github.com:xpppppppppp/agent-skills.git
# copy the skill you want
cp -r agent-skills/software-dev-orchestrator ~/.agents/skills/
```
