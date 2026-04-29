# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # serve locally via npx serve (no install needed)
npm run format   # format with prettier
npm run lint     # check formatting without writing
```

No build step — the project is a single static HTML file served as-is.

## Architecture

Everything lives in `sameen-portfolio.html`: markup, CSS, and (if added) JS are all inline. There is no bundler, no framework, and no JavaScript currently.

**Sections (top to bottom):**
- `.hero` — full-viewport gradient hero with grain overlay, nav, name, status pills, scroll cue
- `.section-work` — numbered work list, each entry is a `<a class="work-entry">` grid row
- `.section-about` — two-column grid: bio (left) + fact table (right)
- `.section-now` — teal `/now` banner strip

**Design tokens** are CSS custom properties on `:root` (lines 14–24). Always use these variables rather than raw hex values when editing colors.

**Typography:** Cormorant (serif, display/headings) + DM Sans (sans-serif, UI/body). Both loaded from Google Fonts. Cormorant is used with `font-weight: 300` and italic for editorial feel; never bold it.

**Responsive:** single breakpoint at `768px` via a single `@media` block near the bottom of `<style>`. Mobile hides `.work-right` and collapses `.section-about` to one column.

**Animations:** pure CSS — `ripple` (status pulse dots) and `scanline` (scroll cue track). No JS scroll or intersection logic yet.
