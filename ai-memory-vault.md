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

First ask for the exact absolute local path where the vault will live. Repeat that path back and get confirmation before creating files. Never leave `[VAULT PATH]` or another placeholder in a generated instruction file.

Interview the person about: their name and preferred agent behavior, active ventures and projects, key people, current priorities, recurring work, writing preferences, and which AI tools will share the vault.

Show the proposed structure and wait for an explicit yes before creating files.

## Create

Create `VAULT-INDEX.md`, `Active Priorities.md`, `00 - Inbox/Agent Tasks.md`, `01 - Daily Notes/`, project folders, `07 - Personal/`, `08 - Archive/`, and `09 - Resources/`. Add a folder index whenever an area becomes substantial.

Create `AGENTS.md` in the vault root from `templates/AGENTS.md`. Replace `[VAULT PATH]` with the confirmed absolute path to this person’s vault before writing the file. The generated `AGENTS.md` must point every AI to that exact vault and require this startup sequence:

1. Read `VAULT-INDEX.md`.
2. Read yesterday's daily note.
3. Read `Active Priorities.md`.
4. Read `00 - Inbox/Agent Tasks.md`.

If the person uses Claude, also create `CLAUDE.md` in the vault root from `templates/CLAUDE.md`, replacing `[VAULT PATH]`, `[AGENT NAME]`, `[ROLE]`, and `[PERSON NAME]` with the person’s confirmed values. Do not create these files until after the person approves the proposed structure.

### Install the same guidance at the tool level

Vault-root instructions work only when an AI starts inside that folder. After the person approves the structure, make tool-wide installation the required final setup step. Install or update a clearly marked **AI Memory Vault** block using the confirmed path for every applicable installed tool:

- **Codex:** `~/.codex/AGENTS.md`
- **Claude Code:** `~/.claude/CLAUDE.md`

Use `templates/TOOL-WIDE-VAULT-GUIDANCE.md` as the source for the block, replacing every `[VAULT PATH]` placeholder first. The block must contain the vault path and the same read-first startup sequence. It makes the vault available to every session of that tool, even when the session begins outside the vault.

Never overwrite unrelated user instructions. If the destination already exists, append one marked block at the end. If it already contains the exact markers below, update only that marked block in place; otherwise append a new marked block:

```markdown
<!-- AI-MEMORY-VAULT:START -->
... generated vault guidance ...
<!-- AI-MEMORY-VAULT:END -->
```

If a selected tool is not installed, record it as not applicable. If the person explicitly declines installation or the AI cannot write a home-directory configuration file, provide the fully generated marked block and the exact destination path for the person to paste manually. Confirm which tool-level files were successfully installed, updated, not applicable, explicitly declined, or still need manual copy/paste. Do not report the setup fully complete while an applicable tool-wide install is still pending.

## Operating rules

- Every created note has YAML frontmatter and an attribution stamp.
- Persist meaningful decisions and outcomes at checkpoints.
- Update relevant folder indexes in the same pass.
- Use the shared agent-task queue for work passed between AI tools.
- Do not silently overwrite, delete, archive, publish, or expose personal vault content.
- Use clear, direct, practical language.
