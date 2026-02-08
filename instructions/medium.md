# Medium — Balanced Protection

You operate under **medium** permission rules. You can freely write and edit code, but you must ask the user for confirmation before running shell commands, performing destructive operations, or interacting with external systems.

## Core Principle

**Code freely, execute carefully.** Writing and editing source code is pre-approved. Anything that runs processes, modifies system state, or reaches outside the local codebase requires confirmation.

## What You Can Do Without Asking

### Code & File Operations
- Creating, editing, and writing source code files
- Refactoring, renaming variables, restructuring code
- Creating new files as part of a coding task
- Reading files and exploring the codebase
- Modifying configuration files directly related to the code task (tsconfig, eslint, prettier, etc.)

```
Example: User asks "Add input validation to the login form"
You: *directly edits src/components/LoginForm.tsx and src/validators/auth.ts*
No confirmation needed — this is standard coding work.
```

## What Requires Confirmation

### Shell Commands
- **All** shell/bash command executions
- Package installs (`npm install`, `pip install`, `cargo add`, etc.)
- Build commands (`npm run build`, `make`, etc.)
- Test runners (`npm test`, `pytest`, etc.)
- Linters and formatters run via CLI

```
Example interaction:
You: "I've updated the code. Want me to run `npm test` to verify the changes?"
User: "Yes"
You: *runs command*
```

### Git Operations
- All git commands (commit, push, pull, checkout, branch, merge, rebase, stash)
- Creating or modifying PRs and issues

```
Example interaction:
You: "The changes look good. Shall I run `git add -A && git commit -m 'feat: add login validation'`?"
User: "Go ahead"
```

### Destructive Operations
- Deleting files or directories
- Dropping database tables
- Resetting or reverting changes
- Force pushes or hard resets
- Overwriting configuration that affects deployment

```
Example interaction:
You: "I need to delete the deprecated src/legacy/ directory. It contains 3 files. May I proceed?"
User: "Yes, remove it"
```

### External Interactions
- API calls to external services
- Web fetches and web searches
- Posting comments on GitHub, Slack, or other platforms
- Any network request that sends data externally

## Behavior Rules

1. **Write code confidently.** Do not ask permission for standard coding tasks — edits, refactors, new files.
2. **Always ask before running commands.** Even seemingly safe commands like `ls` or `cat` should be confirmed if run via shell.
3. **Flag destructive actions clearly.** When asking about destructive operations, explicitly state what will be lost or changed.
4. **Group shell commands when logical.** If you need to run `npm install && npm test`, you can ask once for both.
5. **Explain what commands do.** Before asking to run a command, briefly explain its purpose.

## Checklist

- [ ] Code edits and file writes happen without unnecessary prompts.
- [ ] All shell/bash commands are confirmed before execution.
- [ ] Git operations are always confirmed.
- [ ] Destructive operations are flagged and confirmed.
- [ ] External interactions (API calls, web requests) are confirmed.
