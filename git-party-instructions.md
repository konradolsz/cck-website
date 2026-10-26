# Git Party

Welcome to the Web 3 Git Party!

Today's challenge is to build and deploy a website for a new creative coding club in Kortrijk,
Belgium: Creative Code Kortrijk, or CCK. As its founders, you make this a team effort, and of
course you manage it with Git and GitHub Flow.

[Let's git ready to rumble!](https://www.youtube.com/watch?v=nendMLrpI-s&t=20s)

## Working with your agent

Your agents are allowed, and expected. Each of you works in your own clone, with your own agent
session. That is three people and three agents in one repository, so the merge conflicts are
real.

- **You resolve conflicts and merge pull requests, not your agent.** When `main` and your branch
  conflict, your agent may propose a resolution, but read the result before you commit: an agent
  that "resolves" a conflict by deleting your teammate's work is the classic failure of today. The
  merge itself is a click on the pull request on GitHub, by one of you, after looking at it. Don't
  let your agent merge for you.
- **Keep your failure log going.** Every time your agent gets something wrong today, add it to the
  log: a screenshot or a snippet, and what was wrong. You need it for the `AGENTS.md` workshop
  after the autumn break. Do not arrive there empty-handed.

## Challenge 0: Team up

Divide yourselves into teams of **three**.

## Challenge 1: Set up the project (one per team)

One team member completes the following steps:

- open the starter project in your code editor
- initialize a new git repository
- create a new repository on GitHub and push the local repository to GitHub
- [add the other team members as collaborators to the GitHub repository](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository)
- make your repository public.

The other two clone the repository as soon as they are invited.

Provide the URL of your GitHub repository via [this form](https://forms.gle/3g8qDxmv8gfZYwyWA).

The leaderboard is updated every 10 minutes: [leaderboard](https://repo-leaderboard.pages.dev/)

## Challenge 2: Readme file (one per team)

- One team member creates a feature branch named `feature/readme`.
- On that branch, create a `README.md` file in the root of the repository, with the names of all
  team members.
- Commit, push, and open a pull request to merge the feature branch into `main`.

## Challenge 3: A shared `AGENTS.md` (all team members, at the same time)

Your agents will work in the same project all afternoon, so they need the same facts. Each of you
writes the team's `AGENTS.md` at once, which is exactly why this goes wrong.

- Everyone pulls `main` and creates their own branch: `feature/agents-<your-name>`.
- Each of you, with your own agent, creates an `AGENTS.md` in the root of the repository with two
  sections: **Project** (what this site is, who it is for) and **Stack & constraints** (Astro,
  content collections, no CSS framework, ...). Facts only, no rules yet: that is the workshop's job.
- Commit, push and open a pull request each.
- The first pull request merges cleanly. The second and third do not: three people created the
  same file. Resolve the conflict together, keep the best lines from each version, and make sure
  all three of you show up in the history of `AGENTS.md`.

## Challenge 4: Build the CCK website (all team members)

The site has three content collections: Workshops, Foundations and Team. There is also a News
collection, but that is for a later challenge.

Have a look at `src/content.config.ts`. It holds the configuration of the content collections:
when a field is missing in a markdown file, the build fails.

Every team member takes care of one collection, on a separate feature branch. When you are done,
open a pull request to merge your branch into `main`. Resolve any merge conflicts that come up,
and pull the latest `main` at the end.

### Placeholders

The code contains placeholders in the form `##WHAT-SHOULD-BE-HERE##`. Replace them with the real
content. You don't have to edit CSS or write plain HTML, but you do have to write some logic in
the provided files.

### Workshops (student 1)

- Create a feature branch named `feature/workshops` from `main` and work on that branch.
- Add the `Workshops` component to the `/index` page.
- List all the workshops in the `Workshops` component (see `src/content.config.ts`).
  - Use the `WorkshopCard` component to display the workshop data.
- Show all the necessary data in the `WorkshopCard` component.
- Provide the detail page; use the id as a dynamic route parameter.
  - There is a starter file in `resources/workshops/detailpage`.

### Foundations (student 2)

- Create a feature branch named `feature/foundations` from `main` and work on that branch.
- Add the `Foundations` component to the `/index` page.
- List all the foundations in the `Foundations` component (see `src/content.config.ts`).
  - Use the `FoundationsCard` component to display the foundations data.
- Show all the necessary data in the `FoundationsCard` component.
- Provide the detail page; use the id as a dynamic route parameter.
  - There is a starter file in `resources/foundations/detailpage`.

### Team (student 3)

- Create a feature branch named `feature/team` from `main` and work on that branch.
- Feel free to change the markdown files to match the members of your team.
- Add the `Team` component to the `/index` page.
- List all the team members in the `Team` component (see `src/content.config.ts`).
  - Use the `TeamCard` component to display the team member data.
- Show all the necessary data in the `TeamCard` component.
- Provide the detail page; use the id as a dynamic route parameter.
  - There is a starter file in `resources/team/detailpage`.

## Challenge 5: News (all team members, one news item each)

- Every team member creates a feature branch for their news item from `main`.
- Everyone adds one news item to `src/content/news/`. Pick one of the three in `resources/news`.
- Decide who implements what:
  - Define the news collection in `src/content.config.ts`. Hint: look at the other collections,
    and don't forget to export it.
  - The full content of every item is listed on the `/news` page.
    - Find out how to get the *Content* of a markdown file on that page. That is something else
      than its frontmatter data.
  - Sort the items by date, newest first.
  - Use `.toDateString()` or `.toISOString()` to format the date of a news item.

## Challenge 6: Hide the code! (all team members)

This is a rather boring website for a creative coding club, so let's add some wordplay on *code*.
Visitors have to find the hidden digits of a 4-digit code somewhere on the website. Each of you
hides at least one digit in your part of the website: not immediately visible, but findable with
a little effort (console logs, hover effects, click handlers...). Document where you hid your
digit in the `README.md` of the project. Each of you creates a new feature branch for this
challenge.

Create a `/code` page that uses the `Code` component, so that visitors can enter the digits they
found. You figure out how to set this up.

## Challenge 7: Deployment (one per team)

- One team member deploys the website to GitHub Pages, so that it is deployed automatically
  whenever `main` changes.
- Follow the steps in the [Astro documentation](https://docs.astro.build/en/guides/deploy/github/).
  It comes down to adding one workflow file and switching on Pages in the repository settings.

Treat it as a black box today: copy, commit, watch it go green. We open the box in the deployment
class, when you do the same for your portfolio.

## Award ceremony

Info will follow.

![Award](./readme-assets/award.jpg)
