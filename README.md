# agent-skills

Personal agent skills collection (OpenCode / agents-compatible). Each skill lives in its own subdirectory with a `SKILL.md`.

## Skills

| Skill | Directory | Description |
|---|---|---|
| è½¯ä»¶å¼€å‘æ€»è°ƒåº¦ | [`software-dev-orchestrator/`](./software-dev-orchestrator/) | Full-pipeline orchestrator: spec â†’ design â†’ plan â†’ implement â†’ test cases â†’ review, dispatching to specialized skills with human gates between phases. |

## Usage

Sync a skill directory into `.agents/skills/` (global: `~/.agents/skills/`, per-project: `<repo>/.agents/skills/`).

```bash
# clone private repo
git clone git@github.com:xpppppppppp/agent-skills.git
# copy the skill you want
cp -r agent-skills/software-dev-orchestrator ~/.agents/skills/
```

## Dispatched skills (used by Èí¼ş¿ª·¢×Üµ÷¶È)

| Skill | Phase |
|---|---|
| `spec-driven-development` | 1 Specify / 3 Plan |
| `writing-design-docs` | 2 Design |
| `springboot-patterns` | 4 Implement |
| `java-springboot` | 4 Implement |
| `spring-boot-openapi-documentation` | 4 Implement (API docs) |
| `java-junit` | 4 Tests / 5 Test cases |
| `code-review` | 6 Review |

> Note: Èí¼ş¿ª·¢×Üµ÷¶È dispatches to these skills at each phase. Copy the whole repo (or the skills you need) into `~/.agents/skills/` so the orchestrator can find them all.
