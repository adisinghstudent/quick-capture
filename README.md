# quick-capture

Claude Code skills for capturing thoughts and issues without breaking flow.

## Skills Included

### `/obsidian` - Quick Note Capture
Instantly capture thoughts to your Obsidian vault with timestamps and tags.

```
/obsidian Buy milk #errands
/obsidian Refactor the auth module #work #urgent
```

### `/github` - Quick Issue Creation
Create GitHub issues from anywhere without leaving your terminal.

```
/github Add dark mode support
/github Fix login bug #bug #urgent
/github [owner/repo] Feature request
```

## Installation

```bash
# Install via npx
npx add-skill quick-capture

# Or manually copy the .md files to ~/.claude/skills/
```

## Requirements

- [Claude Code](https://claude.ai/claude-code) CLI
- [GitHub CLI](https://cli.github.com/) (`gh`) for /github skill
- An Obsidian vault at `~/Notes/` for /obsidian skill (or modify the path in the skill)

## License

MIT
