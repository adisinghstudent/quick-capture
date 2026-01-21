# /obsidian - Quick Capture to Obsidian

Instantly capture thoughts, ideas, or tasks to your Obsidian vault without breaking flow.

## Usage

```
/obsidian Buy milk #errands
/obsidian Refactor the auth module #work #urgent
/obsidian Great idea for a new feature
```

## Instructions

When the user invokes `/obsidian <text>`, capture their thought to Obsidian:

1. **Parse the input**:
   - Extract the main text (everything before hashtags)
   - Extract any tags (words starting with #)

2. **Create or append to the Inbox file**:
   - Path: `~/Notes/Inbox.md`
   - If the file doesn't exist, create it with a header
   - Append the new capture with timestamp

3. **Format**:
   ```markdown
   - [ ] <timestamp> <text> <tags>
   ```

   Example:
   ```markdown
   - [ ] 2024-01-21 14:32 Buy milk #errands
   ```

4. **Confirm** the capture was saved with a brief message

## Implementation

```bash
# Get current timestamp
timestamp=$(date "+%Y-%m-%d %H:%M")

# Append to Inbox.md
echo "- [ ] $timestamp <captured text>" >> ~/Notes/Inbox.md
```

## Notes

- Keep confirmations brief: "Captured to Inbox.md"
- If the user provides no text after `/obsidian`, ask what they want to capture
- Tags are preserved as-is in the captured text
