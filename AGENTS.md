# Repository Guidelines

## Project Structure & Module Organization

This repository is a small static Codex wiki. All user-facing pages live in `codex/` as standalone HTML files:

- `codex/index.html`: table of contents and landing page.
- `codex/usage.html`, `codex/examples.html`, `codex/cheatsheet.html`, `codex/plugins.html`: topic pages.

There is no separate `src/`, `tests/`, or asset pipeline at present. CSS is embedded in each page, so keep shared visual changes consistent across all HTML files that use the same layout, navigation, color variables, and responsive breakpoints.

## Build, Test, and Development Commands

- `python3 -m http.server 8000 --directory codex`: serves the wiki locally at `http://localhost:8000/`.
- `find codex -name '*.html' -print`: lists all wiki pages that should be reviewed after navigation or style changes.
- `git diff -- codex AGENTS.md`: reviews local edits before committing.

No build step is required. Pages can also be opened directly in a browser, but a local server is preferred for checking relative links.

## Coding Style & Naming Conventions

Use HTML5 with lowercase element names and semantic landmarks (`header`, `nav`, `main`, `section`, `footer`). Keep indentation at two spaces, matching the existing files. Use system fonts, CSS custom properties in `:root`, and responsive `@media` rules consistent with the current pages.

File names should be short, lowercase, and descriptive, such as `usage.html` or `cheatsheet.html`. Preserve Japanese page content and navigation labels unless the task explicitly asks for localization changes.

## Testing Guidelines

There is no automated test framework yet. For changes, manually verify:

- Each edited page renders in a browser.
- Top navigation links resolve correctly between pages.
- Mobile breakpoints do not cause overlapping text or clipped content.
- Inline code blocks and tables remain readable.

If adding tooling later, prefer lightweight HTML validation and link checking before introducing a full build system.

## Commit & Pull Request Guidelines

The current history only contains `codex_init`, so no detailed convention is established. Use concise, imperative commit messages that describe the user-visible change, for example `Update Codex usage guide` or `Add plugin recommendations`.

Pull requests should include a short summary, changed pages, manual verification steps, and screenshots for visible layout changes. Link related issues when available.

## Agent-Specific Instructions

Keep edits scoped. Do not add package managers, generated assets, or framework files unless requested. When updating navigation, apply the same link set across all `codex/*.html` pages.
