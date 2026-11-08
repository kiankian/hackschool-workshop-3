# Claude Code version

This setup adds project instructions, an explore command, an exploration skill, and a read-only explorer to [Claude Code](https://code.claude.com/docs/en/overview).

## Set up

You'll need Claude Code installed.

1. If your project already has a `CLAUDE.md` or `.claude/` folder, merge these files in by hand, because copying replaces any files with the same name.
2. From this repo's main folder, run these commands, replacing `/path/to/project` with your project's folder:

   ```sh
   cp claude-code/CLAUDE.md /path/to/project/
   cp -R claude-code/.claude /path/to/project/
   ```

3. If your project has an `AGENTS.md`, add the line `@AGENTS.md` to the top of `CLAUDE.md`. Otherwise Claude Code will stop reading `AGENTS.md`.
4. Open a terminal in your project and run `claude`.

## Try it

Type these inside Claude Code:

| Command | What it does |
| --- | --- |
| `/explore-repo` | Maps the whole project and explains how it fits together |
| `/explore-repo .claude` | Explores one folder |
| `/explore-repo how does the explorer find its skill?` | Answers a question about the project |

It only reads files, so it works on any project, including one with no application code.

## What's in the folder

| File | What it's for |
| --- | --- |
| `CLAUDE.md` | Rules Claude follows in your project; add your own project notes here |
| `.claude/commands/` | The `/explore-repo` command |
| `.claude/skills/explore-procedure/` | The steps and checklist for exploring a project |
| `.claude/agents/repo-explorer.md` | The explorer, which can only read and search files |
| `mcp.json.example` | Optional browser testing setup |

Start Claude Code from the folder that contains `.claude/`. Commands, skills, and agents load from there when a session starts.

## Optional add-ons

Both add-ons download and run third-party code, so look them over before turning them on.

**Browser testing (Playwright):** lets Claude open a real browser to check web changes. You'll need Node.js 22. Copy `mcp.json.example` into your project as `.mcp.json`, then approve it when Claude Code asks. Run `claude mcp list` to check the connection.

**Extra coding guidance (Ponytail):** send these as two separate messages in Claude Code:

```text
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

Start a new session and try `/ponytail-help`. This may apply to your other projects too. To remove it, follow [Ponytail's instructions](https://github.com/DietrichGebert/ponytail/blob/main/INSTALL.md).

## Not tested yet

The explorer, skill, and command haven't been checked in Claude Code or run with a live model yet. Type `/` to confirm `/explore-repo` is listed, then try it.

## Learn more

[Instructions](https://code.claude.com/docs/en/memory) · [Skills and commands](https://code.claude.com/docs/en/skills) · [Subagents](https://code.claude.com/docs/en/sub-agents) · [Browser and other tool connections (MCP)](https://code.claude.com/docs/en/mcp)
