# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A static, no-build marketing site for Julien Galendo, a sports coach. It's three self-contained HTML pages (no JS framework, no bundler, no package.json) deployed via GitHub Pages.

- `index.html` — landing page (hero + links to the other two pages and Instagram). This is the GitHub Pages entry point.
- `JG_trainingProgram.html` — training program details (collapsible cards via inline `<script>`).
- `JG_BookAsession.html` — booking page, links out to Instagram DMs. Uses `JG_bookAsession.png` as a hero background image.

## Development

No build tooling. Edit HTML files directly and open them in a browser (or use a local static server, e.g. `python3 -m http.server`) to preview. There are no tests, linters, or package scripts.

## Architecture notes

- Each page is fully self-contained: CSS lives in a `<style>` block in the `<head>`, no shared stylesheet. Design tokens (colors) are repeated as CSS custom properties (`--orange`, `--yellow`, `--dark`, etc.) at the top of each page's `<style>` block — keep these in sync if changing the color scheme across pages.
- Google Analytics (gtag.js, measurement ID `G-1XRHT0YBKJ`) is embedded in the `<head>` of every page and must stay in sync across all three files if the tracking ID ever changes.
- The landing page is `index.html` (renamed from `index2.html` for GitHub Pages); top-bar "back"/brand links in the other pages point to `index.html`.
