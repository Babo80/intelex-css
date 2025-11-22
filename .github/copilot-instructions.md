<!-- Auto-generated guidance for AI coding agents working in this repo. -->
# Copilot / AI agent instructions — intelex-css

Purpose
- Provide concise, actionable guidance for AI coding agents editing this repository.

Big picture
- This repository currently contains a single stylesheet: `AirLiquideDiamond.css` at the repository root.
- The project is a plain CSS theme/stylesheet (no JS, no build system detected). Changes are generally direct edits to the CSS file and validated by loading an HTML page (or the host app) that uses this stylesheet.

Key files
- `AirLiquideDiamond.css`: single source of truth for UI styles. Inspect this file for selectors, naming conventions, and color usages.

Discoverable patterns & conventions
- Class-centric selectors: Most rules target classes (e.g. `.app-tabs`, `.extra-tabs`, `.selected-tab`). Prefer editing/adding classes rather than relying on element selectors.
- Specific IDs for behavior hooks: `#more-button` is used to position the "More" affordance and its hover-activated dropdown. Keep ID semantics when adding similar affordances.
- CSS-only interactive patterns: Dropdown visibility is implemented using `:hover` (`#more-button:hover .extra-tabs { display: block; }`) instead of JS. Preserve this approach when adding simple interactivity unless a new JS layer is explicitly added.
- Comments are written in French. When editing, preserve the comment language and style to keep author consistency.
- No variable system detected: colors and measurements are hard-coded (e.g. `#0074c1`, `6px`, etc.). If introducing CSS variables or refactors, keep changes isolated and explain trade-offs in PR description.

Developer workflow (what an agent should assume)
- There is no detected build/test tooling in the repo. Typical edit/test cycle:
  - Edit `AirLiquideDiamond.css`.
  - Open or refresh the consuming HTML/app in a browser to visually verify changes.
- If you add new files or scaffolding (tooling, package.json, tests), document them clearly in the PR and include how to run/verify locally.

Editing rules for AI agents
- Make minimal, focused changes. This repo is small — prefer single-purpose commits.
- Preserve existing formatting, comment language (French), and the overall selector granularity.
- When changing color values or sizes that affect global visuals, note the reason and list affected selectors in the PR description.
- If introducing CSS variables, add them at the top of `AirLiquideDiamond.css` and leave a short comment explaining usage and backward compatibility steps.

PR guidance
- Title: short, imperative (e.g., "Fix tab dropdown alignment in `AirLiquideDiamond.css`").
- Body: include what changed, why, and how you verified (browser + screenshot if possible). If the change is visual, attach a screenshot or brief reproduction steps.
- Keep changes atomic: split refactors (e.g., variable introduction) and behavioral fixes into separate PRs.

When unable to proceed
- If you need to add JavaScript or a build process, ask for confirmation. This repository currently expects plain-CSS edits.

Contact / follow-ups
- After making changes, ask the repository owner which pages/apps use this stylesheet so you can run visual checks if needed.

---
If anything in this file is unclear or you want me to expand examples (e.g., show how to add a CSS variable safely), tell me and I will update this guidance.
