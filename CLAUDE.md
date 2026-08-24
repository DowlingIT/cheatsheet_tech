# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build & Serve

Ruby 4.0+ with Bundler required.

```
bundle install
bundle exec jekyll serve
```

Site runs at `http://localhost:4000/cheatsheet_tech/`. Jekyll watches for changes automatically with `serve`.

To build without serving: `bundle exec jekyll build` (output in `_site/`).

## Architecture

Multi-page Jekyll site deployed to GitHub Pages at `https://DowlingIT.github.io/cheatsheet_tech`. No JS except Mermaid.

### Two-level hub/leaf structure

Pages come in two types determined by their `layout` front matter:

**Hub pages** (`layout: hub`) — navigation landing pages that render a grid of cards linking to children. Used for the home page and topic pages that have sub-topics (JavaScript, K8s, PHP, Python).

**Leaf cheatsheet pages** (`layout: cheatsheet`) — the actual printable cheatsheet content, with groups of cards. Used for every sub-topic (JavaScript, TypeScript, React, NextJS, Docker, …) and for standalone topics with no sub-topics (Nano, Vim).

### Site structure

```
index.md                         → hub (home, lists all topics)
javascript/index.md              → hub (topic, lists sub-topics)
javascript/javascript-core/index.md → cheatsheet (leaf, core language)
javascript/browser-js/index.md   → cheatsheet (leaf, DOM & Web APIs)
javascript/nodejs/index.md       → cheatsheet (leaf, Node.js runtime)
javascript/typescript/index.md   → cheatsheet (leaf)
javascript/react/index.md        → cheatsheet (leaf)
javascript/nextjs/index.md       → cheatsheet (leaf)
k8s/index.md                     → hub
k8s/docker/index.md              → cheatsheet (leaf)
  … (compose, swarm, helm, kustomize)
php/index.md                     → hub
php/laravel/index.md             → cheatsheet (leaf)
  … (livewire, filament)
python/index.md                  → hub
python/django/index.md           → cheatsheet (leaf)
nano/index.md                    → cheatsheet (leaf — no hub, has no sub-topics)
vim/index.md                     → cheatsheet (leaf — no hub)
```

### Key files

- `_data/nav.yml` — the entire site navigation tree; every hub page reads from it. Each top-level entry has a `slug`, `title`, `description`, and `children` list (empty list `[]` for Nano/Vim). Adding or renaming a topic/sub-topic means editing only this file plus creating the corresponding page(s).
- `_layouts/hub.html` — hub layout; renders `.topic-grid` of child links. For the home page (`page.topic` absent) it renders top-level nav entries; for a topic hub it renders that topic's `children`.
- `_layouts/cheatsheet.html` — cheatsheet layout; loops over `page.groups`, filters `site.sections` by `page.subtopic` and group name. Renders breadcrumb back to parent hub when the topic has children.
- `_includes/nav.html` — shared top nav bar (site-wide, hidden in print); lists all top-level topics from `_data/nav.yml`; highlights active topic via `page.topic`.
- `_sections/<topic>/<subtopic>/*.md` — content cards; `subtopic` and `group` front matter fields are how the cheatsheet layout picks them up.
- `_config.yml` — `baseurl`, `last_updated`; the `sections` collection has `output: false`.
- `assets/css/style.css` — all styling including `@media print` block.

### How the cheatsheet layout works

1. `page.subtopic` is the unique card filter key — the layout runs `site.sections | where: "subtopic", page.subtopic` to get all cards for this page.
2. `page.groups` (a YAML list in the page's own front matter) controls which groups render and in what order.
3. Each group gets a `<section class="page-group">` with a `.group-cards` grid. Groups with zero matching cards are skipped automatically.
4. Descriptions for hub card blurbs and cheatsheet page subtitles come from `_data/nav.yml` — no separate description field needed in page front matter.

### Heading levels

- `h1` — page title (in header)
- `h2` — group headings inside cheatsheet pages — rendered by the layout
- `h3` — card titles — rendered by the layout from `section.title`
- `h4` — content subheadings inside cards — use `####` in section markdown

### Navigation

`_includes/nav.html` renders on every page (screen only; hidden in print). Active topic highlighting works via `page.topic` front matter — set it to the top-level topic slug on every page (including leaf pages), so the correct nav item highlights regardless of how deep the URL is.

### Extensibility

If a sub-topic like React eventually grows too large for one page, convert its `index.md` from `layout: cheatsheet` to `layout: hub`, add a `children` list to its `_data/nav.yml` entry, and create deeper leaf pages (`react/hooks/index.md`, etc.). The hub/leaf pattern is recursive — no layout changes needed.

## Print-First Design

**Printability is a first-class requirement.** Every content or styling change must be verified against Ctrl+P print preview in a browser (landscape orientation).

### Print rules

- Each group (`.group-cards`) uses `break-inside: avoid` so all cards in a group stay together on the same page
- Group headings (`.page-group-heading`) use `break-after: avoid` to stay with their cards
- Nav bar, breadcrumb, and footer are hidden in print
- Cards must be small enough that a group heading + its card grid row fits on a single landscape page
- `column-span: all` on any element inside print columns causes column balancing that creates dead space — do not use it
- CSS grid (not CSS columns) is used for print layout

### When adding or editing content

- Keep each section markdown file short (~15–25 rendered lines). If a card gets too long, split it into two cards
- Mermaid diagrams are capped at `max-height: 80px` in print; keep diagrams simple
- After any content change, check print preview — verify no blank pages, no orphaned headings, no cards split across pages
- Update `last_updated` in `_config.yml` when content changes

### Print CSS constraints

The `@media print` block in `style.css` overrides screen styles. Key values:
- `@page { size: landscape; margin: 0.4in }` — usable area ~10.2" × 7.7"
- `html { font-size: 8pt }` — base size for print
- Card padding, margins, and font sizes are tightened from screen values
- Code blocks use light background (`#eee`) for print

## Section File Format

Section files live at `_sections/<topic>/<subtopic>/<name>.md`.

```markdown
---
title: Card Title
subtopic: javascript
group: Arrays
order: 1
---

#### Subheading

Description text.

\```
command example
\```
```

Front matter fields: `title` (required), `subtopic` (required, unique leaf slug — must match `page.subtopic` on the corresponding cheatsheet page), `group` (required, must match an entry in that page's `groups:` list), `order` (required, integer sort position within the group), `css_class` (optional, for screen-only styling like `wide`).

Mermaid diagrams go directly in the markdown as `<div class="mermaid">` blocks.

## Cheatsheet Page Front Matter

```markdown
---
layout: cheatsheet
title: JavaScript
topic: javascript
subtopic: javascript-core
groups:
  - Arrays
  - Strings
  - Objects
---
```

Fields: `layout: cheatsheet`, `title` (display name), `topic` (parent topic slug — for nav highlighting and breadcrumb), `subtopic` (unique slug used to filter cards — for Nano/Vim set to the same value as `topic`), `groups` (ordered list of group names; controls which groups render and in what order).

## Hub Page Front Matter

```markdown
---
layout: hub
title: JavaScript
topic: javascript
---
```

For the home page, omit `topic`. For the home page, omit `title` too (falls back to `site.title`).

## Adding a New Sub-topic

1. Add a `children` entry to the relevant topic in `_data/nav.yml` with `slug`, `title`, `description`.
2. Create `<topic>/<subtopic>/index.md` with `layout: cheatsheet`, `title`, `topic`, `subtopic`, and initial `groups` list.
3. Add cards under `_sections/<topic>/<subtopic>/*.md` with matching `subtopic`/`group` front matter.

No layout, nav, or CSS changes needed.

## Adding a New Top-level Topic

1. Add a top-level entry to `_data/nav.yml` with `slug`, `title`, `description`, and `children` (empty list if it will be a standalone cheatsheet page like Nano/Vim, or with children if it needs a hub).
2. Create the page(s) following the patterns above.
