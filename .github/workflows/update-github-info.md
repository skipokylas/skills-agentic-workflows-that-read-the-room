---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: "17 9 * * *"
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use these sources to understand what to update:

- `notes/mona-notes.md`
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Use `web-fetch` to read the public guidance from the GitHub Blog and GitHub Changelog. For repository guidance or reference files, use GitHub repository API tools rather than terminal, CLI, or sandboxed commands.

Update `site/content/github-info.md` with concise, practical updates for readers and include source context when content comes from the GitHub Blog or GitHub Changelog.

Open a pull request for Mona to review. Use a pull request title that mentions Mona or GitHub Info. Do not write directly to `main`; rely on `safe-outputs` with `create-pull-request` so the agent can propose changes without writing to the default branch.
