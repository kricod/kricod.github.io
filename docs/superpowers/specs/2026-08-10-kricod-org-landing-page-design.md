# kricod.github.io — Org Landing Page

**Date:** 2026-08-10
**Status:** Approved

## Purpose

kricod is a newly created GitHub organization. This repo serves the org's
landing page at `https://kricod.github.io`. The page tells a visitor what
kricod is and shows what it has published so far.

The org's mission is deliberately not settled yet. The copy reflects that
honestly — a young open-source org building in the open — rather than
inventing a focus the org has not chosen.

## Approach

A single hand-written `index.html` with inline CSS. No build step, no
dependencies, no CI.

Rejected alternatives:

- **Jekyll + theme.** GitHub Pages runs it natively, but a one-page site
  inherits a generic blog theme and `_config.yml` machinery for no gain.
- **Astro / 11ty + Actions.** A build pipeline and `node_modules` for a page
  with three sections. Overkill.

Org-level Pages repos (`<org>.github.io`) serve from the root of the default
branch, so pushing `index.html` to `main` deploys it.

## Content

### Hero

- Org name: `kricod`
- One-line tagline
- Short paragraph: a young open-source organization, building in the open,
  projects published as they are ready

### Projects

A card grid. One card per published repo.

| Project | Description | Link |
|---|---|---|
| practice-exams | Practice questions and mock exams for IT certifications | https://kricod.github.io/practice-exams/ |

Cards link to a project's live site where it has one, falling back to its
GitHub repo otherwise — a visitor clicking a project wants to use it, not read
its source.

Below the grid, a quiet line noting more projects are on the way.

The grid is structured so adding a project is a single copy-pasted `<article>`
element — no other change required.

### Footer

A copyright line (`© 2026 kricod. All rights reserved.`) on the left and the
GitHub org link on the right. Wraps to two stacked lines on narrow viewports.

The copyright covers this site's content. It says nothing about how kricod's
projects are licensed — each repo carries its own license file.

Explicitly out of scope: a "how to contribute" section and a contact block.
Not requested, and the org has nothing to point contributors at yet.

## Technical Requirements

- **Self-contained.** One `index.html` with an inline `<style>` block. Zero
  external requests — no CDN, no web fonts, no analytics. Nothing to break and
  nothing that tracks visitors.
- **Typography.** System font stack.
- **Responsive.** Multi-column card grid on wide viewports, single column on
  mobile. No horizontal page scroll at any width.
- **Theming.** Light and dark, driven by `prefers-color-scheme`. Colors defined
  as CSS custom properties so the palette lives in one place.
- **Semantics.** Real landmark elements (`header`, `main`, `section`, `footer`),
  one `<h1>`, descriptive link text.
- **Metadata.** A `<title>` and a meta description, so search results and
  chat/social link previews render sensibly.
- **Accessibility.** Text/background contrast at least WCAG AA (4.5:1 for body
  text) in both themes; visible keyboard focus on every link.

## Other Changes

`README.md` is updated from its current single heading to state what the repo
is and link to the live site.

## Success Criteria

1. `index.html` loads standalone in a browser with no network access and
   renders fully.
2. The practice-exams card links to the correct repo URL.
3. The layout holds from a 320px-wide viewport up to desktop with no horizontal
   overflow.
4. Both light and dark themes are legible.
5. Pushed to `main`, the page is live at `https://kricod.github.io`.
