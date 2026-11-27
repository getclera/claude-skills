# Engineering skills

Skills Clera's engineering team uses on its own production stack, rewritten so they work on any codebase.

| Skill | What it does |
|---|---|
| [optimize-postgres-query](./skills/optimize-postgres-query/) | Fixes a slow Postgres query with an `EXPLAIN ANALYZE` baseline, a table of 14 common causes, a validated rewrite or index, and an A/B test proving identical results |

## Install

With the [skills CLI](https://skills.sh) (Claude Code, Codex, Cursor and other agents):

```bash
npx skills add getclera/claude-skills --skill optimize-postgres-query
```

Or copy `skills/optimize-postgres-query/` into your agent's skills folder (for Claude Code: `~/.claude/skills/` or `.claude/skills/` in a project).
