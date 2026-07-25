# andre-skills

Agent Skills for [Claude](https://claude.com/claude-code) — small, focused instruction sets that change how the model works, not what it knows.

Each skill is a folder with a `SKILL.md` file. Claude loads the skill's full instructions only when the task matches its `description`, so having many installed costs almost nothing.

## Skills

| Skill | What it does | Language |
|---|---|---|
| [`foco`](skills/foco/SKILL.md) | Reshapes every answer for a reader who needs focus and momentum — ADHD, overload, or just in a hurry. Leads with the next concrete action, numbers multi-step work, restates state between turns, cuts tangents, gives specific time estimates. | 🇧🇷 pt-BR |

## Install

Copy the skill folder into your skills directory:

```bash
git clone https://github.com/andrealb92/andre-skills.git
cp -r andre-skills/skills/foco ~/.claude/skills/
```

Skills in `~/.claude/skills/` are available in every project. For a single project, use `.claude/skills/` inside the repo instead.

Restart Claude Code (or start a new session) and the skill is picked up automatically.

## Why `foco` exists

Most assistant output is optimized to sound complete. That works against you when your bottleneck is starting, not understanding.

`foco` enforces a different shape:

- The first line is something you can **do**, not context you have to read through.
- Anything requiring action from you ends in a single, self-contained **FAÇA AGORA** block — nothing after it.
- Time estimates are specific (`15 minutes`), never vague (`some work`).
- Finished work is stated as a visible win, not buried in a summary.

It deliberately breaks its own brevity rules when you ask for an explanation, when a destructive action needs confirmation, or when debugging is going in circles.

## Writing your own skill

Minimum viable skill — a folder, one file:

```
skills/my-skill/
└── SKILL.md
```

```markdown
---
name: my-skill
description: One sentence on what it does, plus explicit triggers for when to use it. This is the only part Claude reads before deciding to load the skill, so it has to earn the load on its own.
---

# My Skill

Instructions go here.
```

The `description` is the whole game. It is the only text the model sees when deciding whether to load the skill, so name the situations that should trigger it rather than describing the skill abstractly.

## Contributing

Issues and PRs welcome. If you're proposing a new skill, include a short before/after showing what it changes in practice.

## License

MIT — see [LICENSE](LICENSE).
