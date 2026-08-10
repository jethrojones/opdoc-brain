---
name: ai-memory-vault
description: Build a shared Markdown memory vault for multiple AI tools. Adapted from Jared Rhodenizer's AI Memory Vault.
license: CC-BY-NC-SA-4.0
---

# AI Memory Vault Builder

Build an Obsidian vault that serves as the durable, shared memory for every AI tool the person uses.

## Principles

1. The vault is the memory. Do not create competing per-tool memory systems.
2. Hold only the current task in context; retrieve everything else from the vault on demand.
3. The vault is for AI agents to maintain and for the person to read whenever they want.
4. Notes are Markdown; Obsidian is a convenient viewer, linker, and search interface, not a requirement.
5. Project source code belongs in Git repositories. The vault stores orientation, decisions, playbooks, and references.
6. The vault index must stay short. It orients an AI quickly and links to deeper notes; regularly prune repetition and stale detail.

## Before writing

Confirm vault read/write access. If `VAULT-INDEX.md` already exists, do not overwrite it. Ask whether to extend, migrate, or stop.

Interview the person about: their name and preferred agent behavior, active ventures and projects, key people, current priorities, recurring work, writing preferences, and which AI tools will share the vault.

Show the proposed structure and wait for an explicit yes before creating files.

## Create

Create `VAULT-INDEX.md`, `Active Priorities.md`, `00 - Inbox/Agent Tasks.md`, `01 - Daily Notes/`, project folders, `07 - Personal/`, `08 - Archive/`, and `09 - Resources/`. Add a folder index whenever an area becomes substantial.

Create boot guidance from `templates/AGENTS.md`. It must point every AI to the vault and require this startup sequence:

1. Read `VAULT-INDEX.md`.
2. Read yesterday's daily note.
3. Read `Active Priorities.md`.
4. Read `00 - Inbox/Agent Tasks.md`.

## Operating rules

- Every created note has YAML frontmatter and an attribution stamp.
- Persist meaningful decisions and outcomes at checkpoints.
- Update relevant folder indexes in the same pass.
- Use the shared agent-task queue for work passed between AI tools.
- Do not silently overwrite, delete, archive, publish, or expose personal vault content.
- Use clear, direct, practical language.
