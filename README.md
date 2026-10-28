# Intentional UI

An [Agent Skill](https://agentskills.io) for creating, reviewing, and improving frontend UI/UX. It steers away from generic AI-generated design (decorative eyebrows, purple gradients, emoji icons, tiny low-contrast text, fabricated proof) toward product-specific, readable interfaces.

See [`skills/intentional-ui/SKILL.md`](skills/intentional-ui/SKILL.md).

## Install

### Any agent (Claude Code, Codex, Cursor, …)

```sh
npx skills add SoAp9035/intentional-ui
```

### Claude Code plugin

```
/plugin marketplace add SoAp9035/intentional-ui
/plugin install intentional-ui@intentional-ui
```

### Manual

Personal (all projects):

```sh
mkdir -p ~/.claude/skills/intentional-ui && curl -fsSL https://raw.githubusercontent.com/SoAp9035/intentional-ui/main/skills/intentional-ui/SKILL.md -o ~/.claude/skills/intentional-ui/SKILL.md
```

Project only (run in the project root):

```sh
mkdir -p .claude/skills/intentional-ui && curl -fsSL https://raw.githubusercontent.com/SoAp9035/intentional-ui/main/skills/intentional-ui/SKILL.md -o .claude/skills/intentional-ui/SKILL.md
```

The skill activates automatically on UI tasks, or invoke it with `/intentional-ui`.
