# AGENTS.md

## Project

Creative Code Kortrijk (CCK) is a creative coding club in Kortrijk, Belgium.

The website is for people who are interested in creative coding and want to learn more about the
club. It contains workshops, foundations (the club's values), information about the team and news.

- Audience: artists, designers, students and makers who want to find workshops, learn the club's
  foundations and meet the team.
- Built by a team of 3 DEVINE (Howest) students (Henrijs, Konrad, Martin) during the Web 3 Git
  Party, using GitHub Flow (feature branch, pull request, merge to `main`).
- Challenge instructions: `git-party-instructions.md`.
- Design: Figma (link in `README 2.md`), based on the Positivus community landing page.
- Deploy target: GitHub Pages, auto-deploy on `main` (Challenge 7, not set up yet).

## Stack & constraints

- Astro 7 (`astro` ^7.4.0), static site, ESM (`"type": "module"`). Node 24 / npm.
- Scripts: `npm run dev` (dev server, `--host`), `npm run build`, `npm run preview`.
- The project uses Astro content collections. Workshops, Foundations and Team are separate
  collections; content is stored in Markdown files.
- Collection schemas are defined in `src/content.config.ts` (`glob` loader + Zod):
  - `workshops`: `title`, `image` (from `src/content/workshops/*.md`)
  - `foundations`: `title`, `description` (from `src/content/foundations/*.md`)
  - `team`: `name`, `function`, `bio`, `pic` (from `src/content/team/*.md`)
  - `news`: not defined yet (Challenge 5); sample items in `resources/news/`.
  - A missing frontmatter field fails the build.
- Images are referenced from frontmatter via the `image()` schema helper, with paths relative to
  the markdown file; files sit in each collection's `img/` folder.
- Pages: `src/pages/index.astro`, `news.astro`, `about.md`. Layouts: `src/layouts/Base.astro`
  (header, footer, global styles), `Markdown.astro`.
- Components in `src/components/`: section + card pairs (`Workshops`/`WorkshopCard`,
  `Foundations`/`FoundationsCard`, `Team`/`TeamCard`), plus `Header`, `Footer`, `Hero`,
  `ArrowLink`, `Code`.
- Detail-page starters (dynamic route by id) in `resources/{workshops,foundations,team}/detailpage`.
- Placeholders in the form `##WHAT-SHOULD-BE-HERE##` still need real content.
- The project does not use a CSS framework: plain CSS in `src/styles/reset.css`, `global.css`
  (custom properties: colors, fluid type `--fs-*`, spacing `--sp-*`), `markdown.css`, plus scoped
  `<style>` blocks in components. Font: Space Grotesk via `@fontsource-variable`.
- No UI framework (no React/Vue/Svelte), only `.astro` components.
- TypeScript: `astro/tsconfigs/base`, `strictNullChecks`.
