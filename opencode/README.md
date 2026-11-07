# OpenCode version

This setup adds project instructions, review and ship commands, and a reviewer to [OpenCode v2](https://dev.opencode.ai/v2/docs/).

## Set up

You'll need OpenCode v2 installed.

1. If your project already has an `AGENTS.md` or `.opencode/` folder, merge these files in by hand, because copying replaces any files with the same name.
2. From this repo's main folder, run these commands, replacing `/path/to/project` with your project's folder:

   ```sh
   cp opencode/AGENTS.md /path/to/project/
   cp -R opencode/.opencode /path/to/project/
   ```

3. Open a terminal in your project and run `opencode`.
4. Type `/connect` to sign in to an AI provider, then `/models` to choose a model that can use tools. Keep passwords and API keys out of your project files.

## Try it

Type these inside OpenCode:

| Command | What it does |
| --- | --- |
| `/review` | Reviews your current changes |
| `/review path/to/file` | Reviews one file |
| `/ship Add a check for empty input` | Makes the change, tests it, gets it reviewed, and reports back |

`/ship` edits your files. It won't commit or publish anything unless you ask. If you're changing a website, include its URL in your request.

## What's in the folder

| File | What it's for |
| --- | --- |
| `AGENTS.md` | Rules OpenCode follows in your project; add your own project notes here |
| `.opencode/commands/` | The `/review` and `/ship` commands |
| `.opencode/skills/code-review/` | The steps and checklist for a code review |
| `.opencode/agents/reviewer.md` | The reviewer, which is blocked from editing files or running commands |
| `opencode.json.example` | Optional add-on setup |

## Optional add-ons

`opencode.json.example` turns on both add-ons below. Copy it into your project as `opencode.json`, or merge it into your existing config.

Both add-ons download and run third-party code when OpenCode starts, so look them over first.

**Browser testing (Playwright):** lets OpenCode open a real browser to check web changes. You'll need Node.js 22. Run `opencode mcp list` to check the connection. To turn it off, set `disabled` to `true` in its section of `opencode.json`.

**Extra coding guidance (Ponytail):** start a new session and try `/ponytail-help`. To turn it off, delete it from the `plugins` list in `opencode.json`.

## Not tested yet

OpenCode 2.2.5 finds the reviewer, but the setup hasn't been run with a live model. The skill and commands haven't been checked either. Try `/ship` on a small change first.

## Learn more

[Instructions](https://dev.opencode.ai/v2/docs/instructions/) · [Skills](https://dev.opencode.ai/v2/docs/skills/) · [Commands](https://dev.opencode.ai/v2/docs/commands/) · [Agents](https://dev.opencode.ai/v2/docs/agents/) · [Permissions](https://dev.opencode.ai/v2/docs/permissions/) · [MCP](https://dev.opencode.ai/v2/docs/mcp-servers/) · [Plugins](https://dev.opencode.ai/v2/docs/plugins/)
