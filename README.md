# content-creation

A Claude Code plugin with Andrea Dorizza's skills for short-form content. The repo is both the plugin and its marketplace.

| Skill | What it does |
|---|---|
| `short-form-script` | Writes the Italian script for a Reel, TikTok or Short. It drafts one hook per type (eight types), ranks them and lets you pick; the pick decides the skeleton (default, set, *problema → sistema*); then it humanizes the script with `umanizzatore`. |

## Install

```bash
claude plugin marketplace add andreadorizza/content-creation
claude plugin install content-creation@content-creation
```

In the desktop app, add the marketplace `andreadorizza/content-creation`. On this machine you can also add the local folder, `~/Projects/content-creation`.

Restart Claude Code. The skill shows up as `content-creation:short-form-script`.

## Change a skill

1. Edit it under `skills/`, never in the installed copy under `~/.claude/plugins/`.
2. Bump `version` in `.claude-plugin/plugin.json`.
3. Run `claude plugin update content-creation@content-creation` and restart.

Check the manifests with `claude plugin validate .` before you commit.

## What the skills expect on this machine

- `umanizzatore` and `structural-humanizer`, symlinked into `~/.claude/skills/` from `~/Projects/scrivi-come-un-umano`.
- `~/Projects/video-making`, where every video folder, `INDEX.csv` and `reference/PATTERNS.md` live.
- The Notion connector, for Dori's content calendar.

## Sources

`skills/short-form-script/references/content-principles.md` is [aiwithremy/content-principles](https://github.com/aiwithremy/content-principles), a free skill, copied verbatim on 2026-10-26.
