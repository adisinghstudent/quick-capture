# /github - Quick GitHub Issue Creation

Instantly create GitHub issues in the current repo without leaving your terminal.

## Usage

```
/github Add dark mode support
/github Fix login bug on mobile #bug #urgent
/github [owner/repo] Implement caching layer
```

## Instructions

When the user invokes `/github <text>`, create a GitHub issue:

1. **Parse the input**:
   - Check if a repo is specified in `[owner/repo]` format
   - If not, use the current git repo
   - Extract the issue title (main text)
   - Extract any labels (words starting with #)

2. **Determine the repository**:
   ```bash
   # Get current repo if not specified
   gh repo view --json nameWithOwner -q '.nameWithOwner'
   ```

3. **Create the issue**:
   ```bash
   # Without labels
   gh issue create --title "<title>" --body ""

   # With labels (convert #bug to --label bug)
   gh issue create --title "<title>" --body "" --label bug --label urgent
   ```

4. **Return** the issue URL and number

## Examples

**Input**: `/github Add user authentication`
**Action**: Creates issue "Add user authentication" in current repo
**Output**: "Created issue #42: Add user authentication - https://github.com/owner/repo/issues/42"

**Input**: `/github Fix memory leak #bug #critical`
**Action**: Creates issue with labels "bug" and "critical"
**Output**: "Created issue #43 with labels [bug, critical]: Fix memory leak"

**Input**: `/github [anthropics/claude-code] Feature request: vim mode`
**Action**: Creates issue in specified repo
**Output**: "Created issue #100 in anthropics/claude-code"

## Error Handling

- If not in a git repo and no repo specified: "Please specify a repo: /github [owner/repo] <title>"
- If gh CLI not authenticated: "Please run `gh auth login` first"
- If repo doesn't exist: "Repository not found"

## Notes

- Keep it fast - create issues with minimal prompting
- Body is left empty for quick captures (can be edited on GitHub)
- Labels must exist in the repo or the command will fail - warn the user
