---
/audit
---

Run periodically for a project health check.

1. Scan all files for TODO and FIXME comments — list every one found
2. Compare vault/known-issues/ against current code — flag anything resolved or missing
3. Check .windsurf/rules/ conventions are being followed in recent files
4. Flag orphaned files, dead code, or unused imports
5. Check vault/hardware/devices.md is current if this is a hardware project
6. Output a prioritized findings list:
   • **Critical**: things that could cause failures
   • **Medium**: technical debt or outdated docs
   • **Low**: cleanup and cosmetic issues
