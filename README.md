# GitCMS test environment

Private, real-world content-as-code fixtures for testing GitCMS onboarding,
editing, media handling, editorial workflows, and multiple independent sites in
one repository.

Each `sites/<name>` directory is a source snapshot with its original
content, assets, build configuration, dependency lockfiles, and upstream notices.
These are ordinary files in this repository: no submodules, nested repositories,
or dependency on upstream Git history.

| Site root | Framework | Source | Main content locations |
| --- | --- | --- | --- |
| `sites/danto-hugo` | Hugo | [Waishnav/danto-hugo](https://github.com/Waishnav/danto-hugo/tree/c16d60e2a062ec11c2ce8bf40daf6a77c902c633), requested initial state `c16d60e` | `content/posts`, `content/authors` |
| `sites/pinggy` | Hugo | [Pinggy-io/pinggy_website](https://github.com/Pinggy-io/pinggy_website/tree/b79075276b7bafc3e9c7bbfbbf1bfe733a8faf0c) | `content/blog`, `content/docs`, other `content` sections |
| `sites/astro` | Astro | [withastro/astro.build](https://github.com/withastro/astro.build/tree/8ca3ba6b65de3e981ec1aecde8371c39e5d8aaba) | `src/content/blog`, `src/content/pages`, `src/content/caseStudies`, other collections |
| `sites/plausible` | Jekyll | [plausible/website](https://github.com/plausible/website/tree/a06510cbe08adbd1d51c4a69597998ffe9c0a7c1) | `_posts`, `_articles`, `_changes`, root pages |
| `sites/inngest` | Next.js | [inngest/website](https://github.com/inngest/website/tree/a2e1e25368f889e761aa3715f433e2a9d6a5f620) | `content/blog`, `content/changelog`, `content/customers`, `pages/docs` |
| `sites/opencode` | Astro | [anomalyco/opencode — services/www](https://github.com/anomalyco/opencode/tree/e31136bdbdb43e934d8bbd81e75a2065a2625699/services/www) | `src/docs/content` (nested MDX docs), `src/pages` (website routes) |

Inngest supplies a real product marketing and documentation site with a substantial
file-based MDX corpus, rather than a starter template. Plausible supplies Jekyll
coverage in addition to the requested Hugo, Astro, and Next.js examples.

## Using the fixtures

Connect this repository to GitCMS and onboard each directory as a separate site.
The existing five sites have repository-owned configuration under `.gitcms`.
OpenCode is newly imported without pre-generated GitCMS configuration, so it can
exercise discovery and onboarding.

Content paths and assets are relative to each site's root. Preserve that boundary
when testing collection detection, entry saves, and media paths. Use a separate
branch for each test run when a clean baseline is needed; `main` initially holds
the imported source snapshots.

To work with an individual website, run its documented commands from that site's
directory and follow its upstream README and runtime requirements. There is no
root workspace or shared build process. Original workflow files remain inside
site directories, so they are not active repository-root GitHub workflows.

## Provenance and verification

`sources.json` records the full upstream commit for every snapshot. All sources
other than Danto use their default branch tip at import time. OpenCode imports
only `services/www`, with its monorepo source path recorded in `sources.json`.
Its root MIT license and dependency catalog are preserved as `LICENSE` and
`upstream-package.json` inside the fixture; no other OpenCode packages are copied. This repository has
its own Git history; upstream commits are provenance, not imported history.

`verification.json` records the initial snapshot integrity check. Every imported
file path, Git blob hash, executable mode, and symlink was compared with the
pinned upstream Git tree. No snapshot contains a `.git` directory/file, submodule,
or file exceeding GitHub's regular-Git 100 MiB limit. The recorded checks describe
the initial import; later GitCMS edits will naturally differ from upstream.

Website builds and GitCMS end-to-end workflows have not been run as part of this
source import. Some websites use external services and remotely hosted assets;
those integrations remain as upstream configured them. OpenCode also retains its
upstream Bun scripts and `catalog:` dependency references: its schema-generation
scripts expect the upstream CLI/protocol packages. This is a faithful content and
website source fixture, not a standalone build extraction. Its generated OpenAPI
files are included, and `upstream-package.json` records the catalog versions.

## Upstream ownership

Source and content retain their upstream ownership and any original licensing,
attribution, and trademark notices. This repository grants no new license to the
imported material. Public source availability does not imply an open-source
license; for example, Inngest's website package declares `UNLICENSED`.
