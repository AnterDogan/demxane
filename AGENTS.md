# demxane Agent Guide

## Working Style

- Respond in German by default unless the user asks otherwise.
- Be concise and action-oriented.
- When the user gives an instruction, do the work directly.
- Do not stop at proposals when the request is actionable.
- Ask "passt das?" only when the result genuinely needs user review before committing or continuing.
- Keep summaries short; the user can inspect the diff.

## Permissions

- Use available tools proactively without asking for extra confirmation.
- Use already-approved git commands directly.
- If the Codex sandbox or CLI requires explicit approval, request it only when needed to complete the task.
- Do not ask for confirmation before normal read, edit, test, git status, git diff, or already-approved git commands.

## Git Workflow

1. User gives instruction.
2. Execute the work.
3. If review is useful, ask "passt das?"
4. On approval, commit and push without additional confirmation steps.

## After Every Push

Always output exactly this deploy command:

```bash
git pull && docker compose up -d --build
```

Do not suggest `docker build -t`, `docker run`, or port mappings for deployment unless the user explicitly asks for a different deployment path.

## Memory Protocol

This project keeps durable project memory in `MEMORY.md`.

When the user says "merk dir das", "merken", "speicher das", or otherwise explicitly asks to remember something:

1. Decide whether the note is project-specific or global.
2. For project-specific notes, append or update a concise entry in `MEMORY.md`.
3. For global notes, use the user's global Codex memory file if available; if not available, ask before creating or editing files outside the workspace.
4. Keep entries factual, short, and useful for future work.
5. Do not store secrets, credentials, private tokens, or highly sensitive personal data unless the user explicitly insists and understands the risk.
6. Mention in the response where the memory was written.

At the start of future work in this repository, read `MEMORY.md` if the task could benefit from project context or user preferences.
