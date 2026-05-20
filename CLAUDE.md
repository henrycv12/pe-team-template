# CLAUDE.md — PE Team Project Template

This is a **project scaffold** for the LG Electronics Tennessee Production Engineering team. It provides the directory structure, workflow files, and AI-assistant conventions that every new PE project should start from. The template itself contains no production code — only documentation structure and workflow prompts.

---

## What This Repo Is

`pe-team-template` is a blank template, not a running application. When you are working in a repo **cloned from this template**, that repo will have real code. If you are working in this repo directly, all `vault/` and `.windsurf/rules/` files contain `[Fill after bootstrap]` placeholders — that is expected.

---

## Repository Structure

```
pe-team-template/
├── CLAUDE.md           ← This file (AI assistant conventions)
├── CONTEXT.md          ← Current project status (fill after bootstrap)
├── AGENTS.md           ← Architecture map (fill after bootstrap)
├── README.md           ← Human-readable project intro
│
├── vault/              ← Persistent institutional memory
│   ├── architecture/   ← System design documents
│   ├── config/         ← Environment and deployment config
│   ├── decisions/      ← Architecture decision records
│   ├── deployment/     ← Deploy runbooks and scripts
│   ├── hardware/       ← Device specs, wiring notes, PLC register maps
│   └── known-issues/   ← Bug log and workaround notes
│
└── .windsurf/          ← Windsurf AI assistant configuration
    ├── rules/
    │   ├── coding-style.md   ← Naming conventions, anti-patterns
    │   ├── structure.md      ← File/folder conventions
    │   └── workflow.md       ← PR, commit, session workflow rules
    ├── skills/               ← Task-specific context loaded automatically
    └── workflows/
        ├── bootstrap.md      ← /bootstrap — initial project setup prompt
        ├── new-session.md    ← /new-session — session startup checklist
        ├── commit.md         ← /commit — commit message and staging guide
        └── audit.md          ← /audit — codebase health check prompt
```

---

## How to Bootstrap a New Project from This Template

1. Clone or copy this repo into your new project folder.
2. Open the project in Windsurf (or Claude Code).
3. Run the `/bootstrap` workflow (paste `bootstrap.md` prompt into the AI panel).
4. The AI reads the real codebase and fills all `[Fill after bootstrap]` placeholders.
5. Review `vault/` and `CONTEXT.md` / `AGENTS.md` for accuracy.
6. Commit with the `/commit` workflow.

**Important**: Never generate placeholder content — every vault file must reflect what was actually found in the codebase. If a section has nothing to document yet, leave it blank rather than inventing content.

---

## Key Files for AI Assistants

### At Session Start — Always Read

| File | Purpose |
|------|---------|
| `CONTEXT.md` | Current project status, what's working, what's broken, in-progress work |
| `AGENTS.md` | Architecture, module map, data flow, external dependencies |
| `vault/quick-reference.md` | (if exists) IPs, credentials, common commands |

### During Work — Reference As Needed

| File | Purpose |
|------|---------|
| `vault/architecture/` | System design decisions and component relationships |
| `vault/hardware/` | Device specs, wiring, PLC register maps, protocol notes |
| `vault/known-issues/` | Bugs, workarounds, deferred items |
| `.windsurf/rules/coding-style.md` | Naming conventions, anti-patterns specific to this project |

---

## Workflow Conventions

### `/bootstrap` (first-time project setup)
Reads the full codebase, fills CONTEXT.md, AGENTS.md, vault/, and .windsurf/rules/. Run exactly once per project. Never commit until the human reviews.

### `/new-session` (start of every AI session)
Reads CONTEXT.md and AGENTS.md, summarizes current state, identifies in-progress work, and confirms what to tackle next.

### `/commit` (before every git commit)
Stages only relevant files, writes a descriptive commit message referencing the "why", updates CONTEXT.md "Recent work" section.

### `/audit` (periodic health check)
Scans vault/ and .windsurf/ for stale content, checks that CONTEXT.md matches actual codebase state, flags outdated decisions.

---

## Rules for AI Assistants Working in Projects Cloned from This Template

1. **Read before writing**: Always read `CONTEXT.md` and `AGENTS.md` at session start. The vault is the source of truth for architecture and hardware details.

2. **Update CONTEXT.md**: After completing work, update the "Recent work" section with a timestamped summary of what changed. This is the session handoff record.

3. **No placeholder content**: If vault files contain `[Fill after bootstrap]`, run `/bootstrap` rather than inventing content.

4. **Vault files are documentation, not code**: Never execute or import from `vault/`. These are markdown reference documents.

5. **Hardware projects**: For PLC/embedded projects, always check `vault/hardware/` before assuming register addresses, IP addresses, or protocol details. Hardware context is never safely guessable.

6. **Secrets**: Never commit credentials, SMTP passwords, or API tokens. If you find them hardcoded, flag the known-issues file and instruct the developer to move them to env vars or a gitignored secrets file.

7. **CONTEXT.md is living documentation**: It records the current *state*, not the history. When something is fixed or completed, remove it from "broken/in-progress" and either archive it in vault/known-issues/ or delete it.

8. **`.windsurf/rules/` apply to this project**: When coding-style.md has been filled for a real project, follow those conventions strictly — they document patterns already in the codebase.

---

## Maintained By

TN PE Team — henrycv12 (henrry.colmenares@lge.com)
