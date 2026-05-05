# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Operating Rules

**AGENTS.md is the authoritative operating manual for this repository.** Read it before making content decisions. It defines: default authority, safety boundaries, the deep guide methodology, content style (Arabic-first), hub standards, and the git workflow preference.

## Project Overview

A static educational content repository — no build system, no dependencies, no package files. Content is authored in Markdown and also delivered as standalone HTML tutorial pages. The root `index.html` is the live hub and homepage.

**Deployment:** Every push to `main` auto-deploys to GitHub Pages via `.github/workflows/pages.yml`. The entire repo root is the artifact — all files are served as-is.

## Content Structure

```
posts/
├── claude-code-complete-guide/   ← Complete (12 chapters + slides.html hub)
├── local-ai-claude-code-guide/   ← In progress
└── openclaw-guide/               ← Complete (single slides.html + MD files)
```

Each guide in `claude-code-complete-guide` has two representations per chapter:
- `XX-chapter-name.md` — authoritative source, human-readable on GitHub
- `XX-chapter-name.html` — standalone interactive HTML version, uses `guide-style.css`

When editing chapter content, update **both** the `.md` and `.html` file.

Guides without numbered chapters (like `openclaw-guide`) use a single `slides.html` as the full interactive tutorial, with supporting Markdown files (`commands.md`, `tips-and-tricks.md`, `troubleshooting.md`) for reference. No paired HTML required for those MD files.

## Hub Page (`index.html`)

The hub is a single self-contained HTML file (Arabic RTL, inline CSS/JS). It holds the guide card grid, search, filters, and `localStorage`-based progress tracking. When adding a new guide or chapter HTML page, update `index.html` to add the card and link. Do not extract the CSS/JS into separate files — the single-file constraint is intentional.

## HTML Tutorial Standard

All HTML tutorial pages follow these conventions:

- RTL Arabic layout (`<html lang="ar" dir="rtl">`)
- Font: `IBM Plex Sans Arabic` (loaded from Google Fonts) + `JetBrains Mono` for code
- Sidebar navigation with active-state JS: `const p=location.pathname.split('/').pop(); document.querySelectorAll('.side a').forEach(a=>{if(a.getAttribute('href')===p)a.classList.add('active')})`
- Copy buttons on all code blocks — **hidden by default, revealed on hover**:
  - Wrap every `<pre>` in `<div class="code-wrap">`, add `<button class="copy-btn" onclick="copyCode('id',this)">نسخ</button>` after the pre
  - CSS pattern: `.code-wrap{position:relative}` + `.copy-btn{opacity:0; top:8px; right:8px}` + `.code-wrap:hover .copy-btn{opacity:1}`
  - JS: `function copyCode(id,btn){navigator.clipboard.writeText(document.getElementById(id).textContent.trim());btn.textContent='تم ✓';setTimeout(()=>btn.textContent='نسخ',2000)}`
- `guide-style.css` in `claude-code-complete-guide/` already contains the copy button styles — chapter HTML files only need the JS injected
- Callout boxes (`.call`, `.call.tip`, `.call.ok`, `.call.warn`), comparison tables, mobile-friendly layout

If tooling rejects a large HTML file, create a lightweight fallback and note the full version as a future improvement (per AGENTS.md).

## Git Workflow

Commit directly to `main` for guide edits and new chapters. Use a branch/PR only for structural changes (new guide skeleton, hub redesign, CI changes). Commit messages should identify the guide and the change, e.g. `Add HTML chapter 07 MCP integrations`.
