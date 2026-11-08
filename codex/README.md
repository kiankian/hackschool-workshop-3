# Codex version

This setup adds project instructions, a review workflow, and a reviewer to [Codex](https://learn.chatgpt.com/docs/agent-configuration/agents-md).

## Set up

You'll need the Codex command-line tool installed.

1. If your project already has an `AGENTS.md`, `.agents/`, or `.codex/` folder, merge these files in by hand, because copying replaces any files with the same name.
2. From this repo's main folder, run these commands, replacing `/path/to/project` with your project's folder:

   ```sh
   cp codex/AGENTS.md /path/to/project/
   cp -R codex/.agents codex/.codex /path/to/project/
   ```

3. Open a terminal in your project and run `codex`.
4. Choose to trust the project if asked. Without that, Codex ignores the reviewer and the browser testing setup.

## Try it

Type these inside Codex. They start with `$`, not `/`:

| Command | What it does |
| --- | --- |
| `$review-changes` | Reviews your current changes |
| `$review-changes path/to/file` | Reviews one file |

Type `/skills` to see what's available.

## What's in the folder

| File | What it's for |
| --- | --- |
| `AGENTS.md` | Rules Codex follows in your project; add your own project notes here, then restart Codex |
| `.agents/skills/review-changes/` | The `$review-changes` command |
| `.agents/skills/code-review/` | The steps and checklist for a code review |
| `.codex/agents/reviewer.toml` | The reviewer |
| `config.toml.example` | Optional browser testing setup |

## The reviewer can still make changes

In Codex, the reviewer is told not to change anything, but nothing technically stops it. As a safety check, run `git status` after a review to confirm nothing changed.

For stronger protection, review in a separate session with `codex --sandbox read-only`. [Codex's permissions docs](https://learn.chatgpt.com/codex/permissions) explain what that blocks.

## Optional add-ons

Both add-ons download and run third-party code, so look them over before turning them on.

**Browser testing (Playwright):** lets Codex open a real browser to check web changes. You'll need Node.js 22. Copy `config.toml.example` into your project as `.codex/config.toml`, or merge it into your existing file.

**Extra coding guidance (Ponytail):** run these in your terminal:

```sh
codex plugin marketplace add DietrichGebert/ponytail
codex plugin add ponytail@ponytail
```

Then run `codex`, type `/hooks`, review and trust its two hooks, and start a new thread. You'll need Node.js for those hooks. This may apply to your other projects too. To remove it, follow [Ponytail's instructions](https://github.com/DietrichGebert/ponytail/blob/main/INSTALL.md).

## Not tested yet

This version was written from the Codex docs and hasn't been run in Codex at all. Start with `/skills` to confirm Codex finds it, then try `$review-changes` on a small change.

## Learn more

[Instructions](https://learn.chatgpt.com/docs/agent-configuration/agents-md) · [Skills](https://learn.chatgpt.com/docs/build-skills) · [Subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents) · [Browser and other tool connections (MCP)](https://learn.chatgpt.com/docs/extend/mcp?surface=cli) · [Configuration](https://learn.chatgpt.com/docs/config-file/config-basic)
