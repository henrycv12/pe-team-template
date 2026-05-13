---
/commit
---

Run before every git commit.

1. Review all changed files — summarize what was modified
2. Verify the entry point runs without errors
3. Check if CONTEXT.md needs updating — update it if project status changed
4. Check if any vault/ files need updating based on changes made
5. Suggest a commit message in this format:

**[area] short description of what changed**

Examples:
- `[dashboard] add alarm history table`
- `[plc] fix reconnection timeout on machine 3`
- `[vault] update known-issues after fixing pump fault`

6. Wait for user confirmation before running git commit and git push
