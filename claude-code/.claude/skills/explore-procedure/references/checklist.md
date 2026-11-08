# Exploration checklist

Apply the items that fit; not every project has code, tests, or a build.

- **Purpose:** What is this for, and who uses it? What does the README claim about its status or testing?
- **Layout:** What does each top-level folder hold? Are there parallel or repeated structures, and why?
- **Instructions and configuration:** Which agent instruction files, `.claude/` contents, MCP configs, and manifests exist? Which files are examples and which are live? What does `.gitignore` keep out?
- **Entry points:** How does someone start using it: setup steps, commands, scripts?
- **Connections:** Which files reference each other? Does every referenced path, command, skill, or agent actually exist?
- **Consistency:** Do the docs match the files? Are parallel copies in sync? Are there stale references to removed things?
- **Risks:** Does anything download or run third-party code, hold credentials, or widen permissions?
- **Evidence:** Is every claim tied to a file? Are inferences labeled as such?
