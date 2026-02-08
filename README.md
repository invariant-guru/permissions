# @invariant.guru/permissions

Permission modes that control how much your AI CLI asks before acting. Choose the level of autonomy that fits your workflow.

## Modes

| Mode | Instruction | Description |
|------|-------------|-------------|
| **Low** | `low` | Ultra-cautious — AI asks confirmation for **every** action (file edits, shell commands, code changes). |
| **Medium** | `medium` | Balanced — AI writes code freely but asks before **shell commands**, git operations, and destructive actions. |
| **High** | `high` | Permissive — AI handles the full dev workflow autonomously, only asks for **dangerous or irreversible** operations. |
| **YOLO** | `yolo` | Full autopilot — AI **never asks** and executes everything end-to-end without interruption. |

## Usage

**Important:** Install only **one** mode at a time. Activating multiple modes will cause conflicting behavior.

### Install a specific mode

```bash
# Ultra-cautious — asks about everything
invariant add instruction:@invariant.guru/permissions/low

# Balanced — asks for shell/dangerous commands only
invariant add instruction:@invariant.guru/permissions/medium

# Permissive — only asks for critical operations
invariant add instruction:@invariant.guru/permissions/high

# Full autopilot — never asks
invariant add instruction:@invariant.guru/permissions/yolo
```

### Switch modes

To switch modes, remove the current one and add the new one:

```bash
invariant remove instruction:@invariant.guru/permissions/medium
invariant add instruction:@invariant.guru/permissions/high
```

## Which mode should I pick?

- **Low** — You're working on critical systems, production code, or you want full visibility into every action the AI takes.
- **Medium** — Best for most developers. You trust the AI to write code but want to approve anything that runs in your terminal.
- **High** — You're comfortable with the AI managing your dev workflow. Good for feature work and prototyping.
- **YOLO** — You want maximum speed. The AI handles everything from code to commit to PR. Best for greenfield projects or when you're reviewing output afterward.

## Author

invariant.guru

## License

MIT
