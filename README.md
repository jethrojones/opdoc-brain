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

1. Read `ai-memory-vault.md` in an AI session with access to an empty or dedicated Obsidian vault.
2. Answer its discovery questions and confirm the proposed structure before it writes anything.
3. Put the generated boot guidance in your AI tool’s project instructions (`AGENTS.md`, `CLAUDE.md`, or equivalent).

## Attribution and license

This project is based on Jared Rhodenizer’s AI Memory Vault and is licensed under the same [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) license. Keep attribution, use it noncommercially, and share adaptations under the same license.
