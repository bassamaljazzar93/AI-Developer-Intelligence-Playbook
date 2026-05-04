# AI Operating Rules

This repository is the official workspace for **AI Developer Intelligence Playbook**.

It stores practical guides, tutorials, commands, strategies, and field notes about AI developer tools, local AI, coding agents, model setup, cost reduction, and workflow optimization.

## Default Authority

When the user asks to create, improve, rebuild, or update content related to this repository, the assistant may act directly without asking for repeated confirmation.

The assistant may:

- Create new folders under `/posts`.
- Create and update Markdown guides.
- Create and update tutorial-style HTML files.
- Create and update README files.
- Create and update repository hub pages such as `index.html`.
- Add navigation links and index entries.
- Improve structure, formatting, clarity, and consistency.
- Add code blocks, commands, checklists, tables, and troubleshooting sections.
- Delete temporary test files created during the current work session.
- Fix broken links inside this repository.

## Safety Boundaries

The assistant must not:

- Add API keys, tokens, passwords, secrets, or private credentials.
- Publish sensitive personal, employment, government, or restricted information.
- Delete existing guides or major folders unless the user explicitly asks.
- Rewrite the whole repository without a clear reason.
- Claim that a command, model, tool, or pricing detail is current without checking when current information matters.
- Add unsafe install commands without explaining what they do or linking them to the commands guide.

## Default Guide Structure

Each new guide should follow this structure unless the user requests otherwise:

```text
/posts/topic-name/
├── README.md
├── commands.md
├── operations-guide.md
├── download-strategy.md
├── slides.html
└── assets/README.md
```

Optional files:

```text
research-notes.md
troubleshooting.md
comparison.md
quick-start.md
```

## Content Style

Default language: Arabic-first.

Use English only when:

- The user asks for English.
- Technical commands, filenames, APIs, or tool names require English.
- A bilingual output is explicitly useful.

Tone:

- Practical.
- Direct.
- Execution-focused.
- No unnecessary theory.
- No hype.
- End with a clear decision or next action.

## Repository Hub Standard

The root `index.html` is the official homepage and tutorial hub for this repository.

Use it to organize and navigate between guides, tutorials, playbooks, and future learning tracks.

When creating or updating a hub page, follow the `tutorial-hub` standard:

- Single self-contained HTML file.
- Arabic-first RTL layout.
- Search bar.
- Category filters.
- Responsive tutorial cards grid.
- Progress aggregation from localStorage when possible.
- Cards for available guides and planned guides.
- Clear links to guide HTML pages and Markdown support files.
- Mobile-friendly layout.
- Theme toggle when practical.

Preferred visual direction:

- Calm Claude-inspired palette.
- Warm cream backgrounds.
- Charcoal text.
- Clay / muted orange accents.
- Soft borders and shadows.
- Comfortable reading experience.
- Avoid aggressive neon unless the specific guide requires it.

## Tutorial HTML Standard

When creating `slides.html` or educational guides, prefer a tutorial-style HTML page rather than static slides.

The page should include, when practical:

- RTL Arabic layout.
- Calm premium tech style.
- Sidebar or section navigation.
- Progress indicator.
- Step-by-step sections.
- Copy buttons for commands.
- Callouts for warnings and tips.
- Tables for comparisons.
- Checklists for execution.
- Mobile-friendly layout.

If a very large HTML file is rejected by tooling, create a lightweight version that still works and keep the larger design as a future improvement.

## Research Standard

For every AI Developer Intelligence guide, answer these questions:

1. What works today?
2. What is the fastest setup?
3. What is free or low-cost?
4. What are the common issues?
5. What models or tools should be used?
6. What commands are needed?
7. What should be tested within 24 hours?

## Decision Rule

Every guide should end with a practical decision:

- Use this.
- Avoid this.
- Test this first.
- Stop here if it does not produce value.

Do not turn research into endless tool exploration.

## Git Workflow Preference

Default behavior:

- Commit directly to `main` for small guide updates.
- Use clear commit messages.
- Create branches or pull requests only for large, risky, or structural changes.

## Repository Identity

Repository name:

`AI-Developer-Intelligence-Playbook`

Owner:

`bassamaljazzar93`

Main path for guides:

`/posts`

Official homepage:

`index.html`
