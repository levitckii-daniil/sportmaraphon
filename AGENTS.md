# AGENTS.md

LLM-readable project guide for `/Users/levitskiydv/Projects/sportmaraphon`.

## Project Summary

This is a static one-page website for a Sport Marafon Fest trip schedule. It uses plain HTML and CSS only: no JavaScript, no build step, no package manager, and no runtime backend.

Live site:
https://levitckii-daniil.github.io/sportmaraphon/

Repository:
https://github.com/levitckii-daniil/sportmaraphon

Remote:
`origin https://github.com/levitckii-daniil/sportmaraphon.git`

## Source Of Truth

Read these files instead of relying on copied content in this document:

- `index.html`: source of truth for page structure, schedule content, event rows, useful links, map link, artist links, and visible text.
- `styles.css`: source of truth for visual design, layout, responsive behavior, typography, colors, event category styling, and free-slot styling.
- `README.md`: human-facing local preview and deployment instructions.

This file should stay short and stable. Do not duplicate the full current schedule, full link list, or CSS details here; inspect the source files above when needed.

## Local Source Images

The files `1.jpg`, `2.jpg`, `3.jpg`, and `4.jpg` are original local reference images used to derive the schedule. They are intentionally untracked and not published, because the website does not display them.

Do not add or publish these images unless the user explicitly asks.

## How The Site Works

The site is one static HTML page:

- Navigation uses anchor links inside `index.html`.
- The schedule is hard-coded in `<article class="day-card">` blocks.
- Each timeline uses `<ol class="timeline">`.
- Each event row uses `<li class="event event--TYPE">`.
- Event categories are represented by classes such as `event--travel`, `event--food`, `event--sport`, `event--music`, `event--relax`, and `event--free`.

Free schedule slots are intentionally represented as rows with a time and an empty label. Check `index.html` for the current exact pattern before editing.

## Design Intent

The intended style is a soft, readable festival schedule:

- warm/lavender light background;
- white cards with subtle borders and shadows;
- large expressive hero heading;
- sticky pill navigation;
- scannable timeline rows;
- event category icons and color accents.

Use `styles.css` as the exact source for fonts, variables, colors, breakpoints, and event-type styling.

## Editing Guidance

Prefer minimal static edits:

- Change content, schedule rows, and links in `index.html`.
- Change visual design only in `styles.css`.
- Keep the site dependency-free unless the user explicitly asks for a framework.
- Do not add JavaScript unless there is a clear interactive requirement.
- Do not add a build tool for simple content or design changes.
- Keep visible page text in Russian unless the user requests otherwise.
- Preserve accessibility attributes such as `aria-label`, section headings, and `rel="noreferrer"` on external links.
- Verify current external facts/links before updating festival information, because official pages can change.

When adding or changing events, reuse existing event type classes from `index.html` and `styles.css` unless a genuinely new category is needed.

## Local Preview

Use a simple static server:

```bash
python3 -m http.server 8080
```

Then open:

```text
http://localhost:8080
```

Use another port if `8080` is occupied.

## Deployment

GitHub Pages is already configured.

Deployment source:
- branch: `main`
- folder: repository root `/`
- build command: none

To deploy updates:

```bash
git status --short --branch
git add index.html styles.css README.md AGENTS.md
git commit -m "Update Sport Marafon schedule site"
git push
```

GitHub Pages should rebuild automatically after push.

Check Pages status:

```bash
gh api "repos/levitckii-daniil/sportmaraphon/pages"
```

## Important Constraints

- Keep the repo static and lightweight.
- Do not publish local JPG source images unless explicitly requested.
- Preserve the existing GitHub Pages setup.
- Prefer content edits over refactors.
- Avoid unrelated design churn when the user asks for schedule or link updates.
