# 🐢 turtle-squad-core

Platform-agnostic source of truth for the TMNT turtle squad. Contains raw turtle bodies and the shared dojo — no platform-specific frontmatter.

## Contents

```
turtles/
  splinter.md       ← Ratman orchestrator
  turtleman.md      ← Siege specialist entry point
  donatello.md      ← Tech/tooling implementer
  leonardo.md       ← Architect/planner
  raphael.md        ← Fast bug fixer
  michelangelo.md   ← Creative lateral thinker
  shredder.md       ← Adversarial gatekeeper
  vernon.md         ← Socratic requirement enforcer
turtle-dojo.md      ← Shared working principles
```

## How it works

Each platform repo includes this repo as a git submodule at `core/` and ships a `build.js` that:

1. Reads bodies from `core/turtles/<name>.md`
2. Stamps platform-specific frontmatter
3. Writes the result to the platform's expected path

**Updating a turtle:** edit `turtles/<name>.md` here, commit, then `git submodule update --remote && node build.js` in the platform repo.

## Platform repos

| Platform | Repo | Format |
|----------|------|--------|
| Claude Code | [tommaone/claude-skills](https://github.com/tommaone/claude-skills) | `plugins/<name>/commands/<name>.md` |
| opencode | [tommaone/opencode-turtle-skills](https://github.com/tommaone/opencode-turtle-skills) | `.opencode/agent/<name>.md` |
| GitHub Copilot CLI | [tommaone/copilot-turtle-skills](https://github.com/tommaone/copilot-turtle-skills) | `agents/<name>.md` |
| Kiro | coming soon | `.kiro/steering/<name>.md` |

## Evolution layer

Turtle **bodies** live here. Turtle **lessons** live locally in `~/.claude/turtle-evolution/<turtle>.md` (or platform equivalent) — never committed here. The turtles never change. They evolve. 🐢
