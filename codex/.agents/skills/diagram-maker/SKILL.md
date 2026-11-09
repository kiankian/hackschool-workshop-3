---
name: diagram-maker
description: Use when the user asks to draw, diagram, visualize, or sketch how something is structured or how it works, such as an architecture, a flow, a sequence of steps, or how files and components connect. Not for charts of numeric data and not for plain explanations without a diagram.
---

# Diagram maker

Turn a structure or process into a rendered Mermaid diagram grounded in the actual files. It does not authorize editing project files.

1. Set the subject: what to draw and at what level (whole project, one folder, one flow).
2. Read the files that define it before drawing. Every node and arrow must come from something you read: a path, a reference, a frontmatter field, an import, or a documented step. Do not draw from assumptions.
3. Read `references/mermaid-conventions.md` in this skill's directory (`.agents/skills/diagram-maker/` from the project root). Use it to pick the diagram type and follow its style and syntax rules.
4. Draw one diagram of at most about 15 nodes. If the subject is bigger, draw the overview and offer to zoom into a part.
5. Reply in exactly this format:

   ````markdown
   ## 📐 Diagram: <short title>

   ```mermaid
   <diagram>
   ```

   **How to read it:** <one or two sentences on what the shapes and arrows mean>

   **Built from:** <the files you read, as paths>

   **Left out:** <anything skipped to keep it readable, or "nothing">
   ````

6. If the user wants a copy in the project, offer to save the Mermaid source to a Markdown file; do not save without being asked.
