---
name: quick-capture
description: Instantly capture thoughts to Obsidian and create GitHub issues without breaking flow
skills:
  - obsidian
  - github
---

# quick-capture

Claude Code skills for zero-friction capture of thoughts and issues.

## /obsidian

Instantly save thoughts to your Obsidian vault with timestamps and tags.

```
/obsidian Buy milk #errands
/obsidian Great feature idea #work #urgent
```

Appends to `~/Notes/Inbox.md` with format:
```
- [ ] 2024-01-21 14:32 Buy milk #errands
```

## /github

Create GitHub issues in seconds without leaving your terminal.

```
/github Add dark mode support
/github Fix login bug #bug #critical
/github [owner/repo] Feature request
```

Creates issues in current repo (or specified repo) with optional labels.

## Requirements

- Claude Code CLI
- GitHub CLI (`gh`) for /github
- Obsidian vault at `~/Notes/` for /obsidian
