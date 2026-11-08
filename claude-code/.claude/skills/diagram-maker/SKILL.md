---
name: diagram-maker
description: Use when the user asks to draw, diagram, visualize, or sketch how something is structured or how it works, such as an architecture, a flow, a sequence of steps, or how files and components connect. Not for charts of numeric data and not for plain explanations without a diagram.
---

# Diagram maker

Turn a structure or process into a rendered Mermaid diagram grounded in the actual files. It does not authorize editing project files; the only file it writes is the page it publishes, in the session's scratchpad.

1. Set the subject: what to draw and at what level (whole project, one folder, one flow).
2. Read the files that define it before drawing. Every node and arrow must come from something you read: a path, a reference, a frontmatter field, an import, or a documented step. Do not draw from assumptions.
3. Read `references/mermaid-conventions.md` in this skill's directory (`.claude/skills/diagram-maker/` from the project root). Use it to pick the diagram type and follow its style and syntax rules.
4. Draw one diagram of at most about 15 nodes. If the subject is bigger, draw the overview and offer to zoom into a part.
5. Render it. If the Artifact tool is available, publish the diagram as a page every time, without asking:
   - Write an HTML file in the scratchpad directory with the diagram inside `<pre class="mermaid">…</pre>`. Artifacts render Mermaid natively, so load no Mermaid library.
   - Under the diagram, put the same "How to read it", "Built from" and "Left out" sections as in the reply below.
   - Follow the Artifact tool's page rules (title, theme tokens, phone width). Wrap the diagram in an `overflow-x: auto` container so a wide flowchart scrolls instead of shrinking.
   - For a follow-up change to the same diagram, republish the same file so the link stays the same.

   If the Artifact tool is not available, skip this step and reply with the text format alone.
6. Reply in exactly this format. Include the `View it` line only when a page was published, and the mermaid block only when none was:

   ````markdown
   ## 📐 Diagram: <short title>

   **View it:** <artifact link>

   ```mermaid
   <diagram>
   ```

   **How to read it:** <one or two sentences on what the shapes and arrows mean>

   **Built from:** <the files you read, as paths>

   **Left out:** <anything skipped to keep it readable, or "nothing">
   ````

7. If the user wants a copy in the project, offer to save the Mermaid source to a Markdown file; do not save without being asked.
