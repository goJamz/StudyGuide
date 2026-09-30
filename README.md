# WOIC Study Guide

A personal study guide authored in Obsidian, published with Quartz, and hosted
on GitHub Pages.

## Local setup

The project pins Node.js with [mise](https://mise.jdx.dev/) and installs its
JavaScript dependencies from `package-lock.json`.

```bash
mise install
npm ci
```

If mise is not installed yet, follow its
[installation instructions](https://mise.jdx.dev/getting-started.html).

## Preview the site

```bash
npx quartz build --serve
```

The local site is available at <http://localhost:8080>.

## Deployment

The workflow in `.github/workflows/deploy.yml` builds and deploys the site when
changes are pushed to `main`. It uploads the generated `public/` directory as a
GitHub Pages artifact and deploys it with GitHub's native Pages actions; it does
not create or publish a `gh-pages` branch.

Before the first deployment, open the repository's **Settings > Pages** page and
set **Source** to **GitHub Actions**. The published site will be available at:

<https://gojamz.github.io/StudyGuide/>

## Write notes

Open `content/` as an Obsidian vault. Study material remains ordinary Markdown,
and Quartz supports the vault's wikilinks, backlinks, tags, and graph.

The initial content areas are:

- `content/lessons/`
- `content/concepts/`
- `content/exam-review/`
- `content/references/`

Project planning notes under `notes/` are intentionally local and excluded from
Git.
