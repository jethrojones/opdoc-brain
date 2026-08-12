# AI Memory Vault

Give every AI you use one durable, local-first memory: an Obsidian vault made of Markdown files.

This is an adapted and expanded derivative of [Jared Rhodenizer’s AI Memory Vault](https://github.com/jaredrhod/ai-memory-vault). It keeps the core idea—plain Markdown as persistent, on-demand AI memory—and adds a cross-agent task queue, explicit startup checks, attribution, repository boundaries, and a delegation workflow.

## What changes in this version

- Every agent starts from the same vault index, recent daily context, active priorities, and agent-task queue.
- The vault index stays short and curated: it is an orientation layer, not a second encyclopedia. Details live in linked notes and are pruned regularly.
- The vault is the only memory system; project source stays in its own Git repository.
- The vault is written primarily for AI continuity. A person can read it whenever useful, without becoming its full-time librarian.
- Agents persist meaningful outcomes, maintain indexes, and leave attribution on created notes.
- A shared task queue coordinates work between different AI tools.

## Use it

1. Open `ai-memory-vault.md` on GitHub and copy the full Builder prompt into an AI session with access to an empty or dedicated vault location.
2. Give the Builder the exact absolute vault path, answer its discovery questions, and confirm the proposed structure before it writes anything.
3. The Builder creates a vault-root `AGENTS.md` with that real path inserted. If you use Claude, it can also create the matching `CLAUDE.md`.
4. As the required final setup step, the Builder installs the same guidance for every session of each applicable tool: Codex at `~/.codex/AGENTS.md` and Claude Code at `~/.claude/CLAUDE.md`. It appends or updates only its marked AI Memory Vault block and preserves any other instructions. If it cannot write a file, it gives you the exact block to paste there.

## Included templates

- `CLAUDE.md` and `AGENTS.md` vault-root boot configurations
- `TOOL-WIDE-VAULT-GUIDANCE.md`, the safe append-only block for `~/.codex/AGENTS.md` and `~/.claude/CLAUDE.md`
- `VAULT-INDEX.md` short orientation layer
- `AGENT-TASKS.md` shared cross-agent queue
- `DAILY-NOTE.md` append-only daily record

## See a working example

Open the fully fictional [Sample Brain Vault](https://github.com/jethrojones/sample-brain-vault) to see the structure, links, daily notes, projects, people, tasks, and Obsidian starter settings in context.

## Attribution and license

This project is based on Jared Rhodenizer’s AI Memory Vault and is licensed under the same [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) license. Keep attribution, use it noncommercially, and share adaptations under the same license.
