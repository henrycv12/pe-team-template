---
description: Triggered when modifying PLC config, sensor parameters, motor settings, or any hardware-related code
---

## Before changing
1. Read vault/hardware/devices.md — confirm device details
2. Read vault/hardware/protocols.md — confirm communication method
3. Read vault/hardware/wiring-notes.md — check for relevant warnings
4. Confirm with user that equipment is in a safe state (LOTO if needed)

## Rules
• Never change PLC IP addresses without updating vault/hardware/devices.md
• Never modify motor parameters without documenting the before/after values
• Always verify communication after any hardware config change

## After changing
• Update vault/hardware/ with new values immediately
• Document reason in vault/decisions/
