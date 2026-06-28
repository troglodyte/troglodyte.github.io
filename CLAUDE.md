# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-file personal portfolio site deployed via GitHub Pages at `troglodyte.github.io`. There is no build step, no framework, no package manager — just `index.html` with inline CSS and JavaScript.

## Development

Open `index.html` directly in a browser to preview. No server needed.

For a quick local server if needed:
```
python3 -m http.server 8080
```

Deploy by pushing to the `main` branch — GitHub Pages publishes automatically.

## Architecture

Everything lives in `index.html`:

- **CSS** — inline `<style>` block using CSS custom properties. The palette is adapted from [taniarascia.com](https://www.taniarascia.com/): warm beige tones (`--beige-0` through `--beige-4`) with a teal accent (`--accent: #0f766e`). Heading font is **Outfit** loaded from Google Fonts; body uses the system font stack.
- **HTML** — sticky frosted-glass nav → hero (name + animated rotating subtitle) → About → Skills grid → Experience timeline → footer.
- **JS** — minimal: sets the copyright year. The rotating subtitle (`Engineer / Team Lead / Mentor / Polyglot`) is driven purely by a CSS `@keyframes` animation on `::after` content.

## Key design decisions

- The animated role in `.hero .subtitle .role::after` cycles through four values using CSS `content` keyframes — no JS required.
- Skill cards use `--bg-alt` (`--beige-1`) backgrounds with `--border` (`--beige-2`) outlines that darken to `--border-hover` (`--beige-3`) on hover.
- The timeline uses a two-column grid (`96px dates | 1fr content`) that collapses to single-column below 560px.
- The nav hides `.nav-links` on mobile (links are duplicated in the hero meta row and footer).
