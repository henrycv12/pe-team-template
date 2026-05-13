---
/bootstrap
---

Run this once when opening a project that has no structure yet.

You are opening a project with NO structure. Your job is to bootstrap it from scratch. Work through every step in order — do not skip any.

## STEP 1 — Read the codebase
Run: `find . -type f | grep -v "__pycache__|.git|node_modules|.env" | sort`

Then read the most important files: entry point, config, main modules, requirements.txt or package.json.

Build a complete mental model of what this project does before creating anything.

**Do not generate placeholder content** — every file you create must reflect what you actually found.

## STEP 2 — Fill CONTEXT.md
Document what this project does, current status, tech stack, key file map, and known issues.

## STEP 3 — Fill AGENTS.md
Document architecture, module responsibilities, data flow, external dependencies, and deployment target.

## STEP 4 — Fill vault/
Populate every vault/ subfolder with real content extracted from the codebase.

For hardware projects fill vault/hardware/devices.md, protocols.md, and wiring-notes.md.

## STEP 5 — Fill .windsurf/rules/
Update coding-style.md, workflow.md, and structure.md based on conventions already present in this codebase.

## STEP 6 — Fill .windsurf/skills/
Update each skill file so that file paths, module names, and pitfalls reflect this actual project.

## STEP 7 — Confirm
Run: `find vault/ .windsurf/ -type f | sort`

Print a one-line summary of every file and its contents.

**Do NOT commit.** The user will review first.
