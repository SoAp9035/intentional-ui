# Intentional UI

An [Agent Skill](https://agentskills.io) for creating, reviewing, and improving frontend UI/UX. It steers away from generic AI-generated design (decorative eyebrows, purple gradients, emoji icons, tiny low-contrast text, fabricated proof) toward product-specific, readable interfaces.

Works with any agent that supports the Agent Skills format. See [`skills/intentional-ui/SKILL.md`](skills/intentional-ui/SKILL.md).

## Install

```sh
npx skills add SoAp9035/intentional-ui
```

The CLI detects your installed agents and asks where to install. Add `-g` to install globally instead of into the current project.

### Manual

Copy `skills/intentional-ui` into your agent's skills directory:

```sh
SKILLS_DIR=~/.agents/skills   # replace with your agent's skills directory
mkdir -p "$SKILLS_DIR/intentional-ui" && curl -fsSL https://raw.githubusercontent.com/SoAp9035/intentional-ui/main/skills/intentional-ui/SKILL.md -o "$SKILLS_DIR/intentional-ui/SKILL.md"
```

## Update

```sh
npx skills check    # list available updates
npx skills update   # update installed skills
```

Manual installs: rerun the `curl` command above.

## Usage

The skill loads automatically on UI tasks; no extra setup is needed.

## License

[MIT](LICENSE)
