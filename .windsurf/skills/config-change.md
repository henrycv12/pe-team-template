---
description: Triggered when modifying settings, environment variables, or connection parameters
---

## Before changing
1. Read vault/config/ — understand current values and their purpose
2. Check vault/known-issues/ for config-related warnings
3. Confirm the change with the user before applying

## Rules
• Never hardcode secrets — use environment variables
• Document every config value in vault/config/ with its purpose and valid range
• Test connectivity after any connection parameter change

## After changing
• Update vault/config/ immediately
• Note the reason for the change in vault/decisions/
