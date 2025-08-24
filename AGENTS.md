# Repository Guidelines

## Project Structure & Module Organization
- Root-level static site:
  - `/index.html`: App launcher (links to apps).
  - `/tictactoe.html`: Tic Tac Toe game (inline CSS/JS, theme toggle with localStorage).
  - `/grades.html`: Grade calculator (inline CSS/JS sliders).
  - `/GEMINI.md`, `/.claude/`: AI context files (non-runtime).
  - No build system or external assets; everything is self-contained.

## Build, Test, and Development Commands
- Run locally (simple server): `python3 -m http.server 8000` then visit `http://localhost:8000`.
- Or open files directly: `index.html` in a browser (use a server if testing `localStorage`).
- Quick preview on macOS: `open index.html`.

## Coding Style & Naming Conventions
- Indentation: 4 spaces for HTML, CSS, and JS blocks.
- HTML: keep semantic where reasonable; prefer minimal, readable markup.
- CSS: define styles in a single `<style>` block per page; class names kebab-case (e.g., `.app-link`).
- JavaScript: camelCase for variables/IDs (e.g., `currentAverage`, `themeToggleBtn`); keep code inline in the page.
- Versions: keep the `.version` footer (e.g., `v1.0.1`) consistent across pages when updating.

## Testing Guidelines
- Manual checks per page:
  - Grades: entering “Current Grade Average” reveals the new average slider and updates values when sliders move.
  - Tic Tac Toe: play PVP and PvAI, verify win/tie detection, statistics increment, “New Game” resets board, theme persists.
- Cross-browser sanity: test in a Chromium-based browser and Safari/Firefox if possible.
- Optional future automation: add Playwright/Cypress e2e tests under `/tests/` (not currently present).

## Commit & Pull Request Guidelines
- Commit style: follow Conventional Commits seen in history: `feat: …`, `fix: …`, `refactor: …`, `style: …`.
- Scope succinctly describes the page or element (e.g., `feat(tictactoe): add dark theme`).
- PRs must include:
  - Summary of changes and rationale.
  - Screenshots/GIFs for UI changes.
  - Testing notes (browsers used, steps to verify).
  - Linked issue (if applicable).

## Security & Configuration Tips
- No secrets or network calls; keep the app offline-first.
- Avoid introducing remote scripts or trackers. If adding assets, prefer local files under `/assets/`.
- When touching theme/state, use `localStorage` keys consistent with existing patterns (e.g., `theme`).

