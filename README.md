# Coding agent setup

A coding agent is an AI tool that can read and change the code in your project. This repo is a ready-made setup that helps one work more carefully: it reads your project first, makes small changes, runs your tests, gets its work reviewed, and reports what it actually did.

## Get started

Pick the tool you use and follow the README in its folder. You only need one.

| Tool | Folder |
| --- | --- |
| Claude Code | [claude-code/](claude-code/README.md) |
| OpenCode | [opencode/](opencode/README.md) |
| Codex | [codex/](codex/README.md) |

## What you get

- **Project instructions:** rules the agent follows every time you use it in that project.
- **A review command:** asks the agent to check your code for bugs and missing tests.
- **A reviewer:** a second agent that checks the work and isn't meant to change anything.
- **Optional add-ons:** browser testing with Playwright, and extra coding guidance with Ponytail.

Any model your tool supports should work, as long as it can use tools.

## How far it's been tested

None of these versions has been run with a live AI model yet, so expect to try it out on a small change first.

| Version | Checked so far |
| --- | --- |
| Claude Code | The tool finds the reviewer, skill, and commands |
| OpenCode | The tool finds the reviewer |
| Codex | Docs only; not tried in Codex itself |

## Changing this repo

Each folder has its own copy of the files. If you change one version, make the same change in the other two.

## License

[MIT](LICENSE)
