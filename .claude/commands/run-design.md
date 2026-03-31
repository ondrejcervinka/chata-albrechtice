Run a two-stage design pipeline on this portfolio project using the Agent tool.

**Stage 1 — Portfolio Agent**
Launch a general-purpose agent with this prompt:
"You are a web designer specializing in 3D artist portfolios. Read the skill file at `.claude/skills/3d-portfolio-design/SKILL.md` and internalize it fully. Then read `index.html`, `style.css`, and `about.html`. Apply the skill guidelines to: $ARGUMENTS. If no task is specified, run a full first-impression audit and implement the highest-impact improvements. Commit your changes with a descriptive message. Work autonomously."

Wait for Stage 1 to complete before continuing.

**Stage 2 — UX Review Agent**
After Stage 1 is done, launch a second general-purpose agent with this prompt:
"You are a UX reviewer. Read the skill file at `.claude/skills/design-ux/SKILL.md` and internalize it fully. Then read `index.html`, `style.css`, and `about.html` in their current state (after recent changes). Do NOT override aesthetic decisions — work within the existing design. Audit for accessibility, visual hierarchy, spacing, contrast, and interaction quality. Fix all issues by priority (critical → important → polish). Reference file:line for each issue. Commit your fixes. Work autonomously."

Report a summary of what both agents changed when done.
