# AGENTS.md

## Project

- Website for Creative Code Kortrijk (CCK), a new creative coding club in Kortrijk, Belgium.
- Audience: people interested in creative coding, who want to see the club's workshops, its
  foundations (values), the team and news.
- Built by a team of 3 DEVINE (Howest) students during the Web 3 Git Party, using GitHub Flow
  (feature branch, pull request, merge to `main`).
- Design: Figma (link in `README 2.md`), based on the Positivus community landing page.
- Deploy target: GitHub Pages, auto-deploy on `main` (Challenge 7, not set up yet).

## Stack & constraints

- Astro 7 (`astro` ^7.4.0), static site, ESM (`"type": "module"`). Node 24 / npm.
- Scripts: `npm run dev` (dev server, `--host`), `npm run build`, `npm run preview`.
- Content collections in `src/content.config.ts`, `glob` loader + Zod schemas:
  - `workshops`: `title`, `image` (from `src/content/workshops/*.md`)
  - `foundations`: `title`, `description` (from `src/content/foundations/*.md`)
  - `team`: `name`, `function`, `bio`, `pic` (from `src/content/team/*.md`)
  - `news`: not defined yet (Challenge 5); sample items in `resources/news/`.
  - A missing frontmatter field fails the build.
- Images are referenced from frontmatter via the `image()` schema helper; files sit in each
  collection's `img/` folder.
- Pages: `src/pages/index.astro`, `news.astro`, `about.md`. Layouts: `src/layouts/Base.astro`,
  `Markdown.astro`.
- Components in `src/components/`: section + card pairs (`Workshops`/`WorkshopCard`,
  `Foundations`/`FoundationsCard`, `Team`/`TeamCard`), plus `Header`, `Footer`, `Hero`,
  `ArrowLink`, `Code`.
- Detail-page starters (dynamic route by id) in `resources/{workshops,foundations,team}/detailpage`.
- Placeholders in the form `##WHAT-SHOULD-BE-HERE##` still need real content.
- Styling: plain CSS, no CSS framework. `src/styles/reset.css`, `global.css` (custom properties:
  colors, fluid type `--fs-*`, spacing `--sp-*`), `markdown.css`. Font: Space Grotesk via
  `@fontsource-variable`.
- No UI framework (no React/Vue/Svelte), only `.astro` components.
- TypeScript: `astro/tsconfigs/base`, `strictNullChecks`.
