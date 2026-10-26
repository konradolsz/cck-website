# AGENTS.md

## Project

- Website for Creative Code Kortrijk (CCK), a new creative coding club in Kortrijk, Belgium.
- Audience: people interested in creative coding (artists, designers, students, makers) who want
  to find workshops, learn the club's foundations and meet the team.
- Built by a team of three (Henrijs, Konrad, Martin) as the Web 3 "Git Party" exercise, using
  GitHub Flow: feature branches, pull requests, merges into `main`.
- Challenge instructions: `git-party-instructions.md`.
- Deployed to GitHub Pages from `main`.

## Stack & constraints

- Astro 7 (`astro` package, ES modules). Scripts: `npm run dev`, `npm run build`, `npm run preview`.
- Content lives in Astro content collections, defined in `src/content.config.ts` with the `glob`
  loader and Zod schemas:
  - `workshops` (`src/content/workshops`): `title`, `image`
  - `foundations` (`src/content/foundations`): `title`, `description`
  - `team` (`src/content/team`): `name`, `function`, `bio`, `pic`
  - `news` (`src/content/news`): not defined yet; source items are in `resources/news`.
- A missing frontmatter field fails the build. Images are referenced relative to the markdown
  file (`img/...`) and validated with `image()`.
- Pages: `src/pages/index.astro`, `news.astro`, `about.md`. Detail pages use the entry id as a
  dynamic route parameter; starter files are in `resources/*/detailpage`.
- Layouts: `src/layouts/Base.astro` (header, footer, global styles), `Markdown.astro`.
- Components in `src/components`: one list component and one card component per collection
  (`Workshops`/`WorkshopCard`, `Foundations`/`FoundationsCard`, `Team`/`TeamCard`), plus `Hero`,
  `Header`, `Footer`, `ArrowLink`, `Code`.
- Placeholders in the form `##WHAT-SHOULD-BE-HERE##` mark content and logic still to write.
- No CSS framework: plain CSS in `src/styles` (`reset.css`, `markdown.css`, `global.css`) and
  scoped `<style>` blocks in components. Font: Space Grotesk via `@fontsource-variable`.
- Design: Figma file linked in `README 2.md`.
