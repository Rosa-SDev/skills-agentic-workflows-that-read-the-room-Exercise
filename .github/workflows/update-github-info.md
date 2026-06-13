---
description: Draft Mona GitHub Info updates from the GitHub Blog and Changelog.
on:
  workflow_dispatch:
  schedule:
    - cron: "17 9 * * *"
permissions:
  contents: read
  issues: read
  pull-requests: read
tools:
  edit:
  web-fetch:
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
network:
  allowed:
    - defaults
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

## Task

Read notes/mona-notes.md first.

Then web fetch:
- https://github.blog/latest/
- https://github.blog/changelog/
- https://awesome-copilot.github.com/workflows/

Use the notes and official GitHub sources to update site/content/github-info.md with concise, practical information for readers. Keep the tone short, useful, and aligned with Mona's editorial angle. Mention the source whenever a change comes from the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows.

Open a pull request for Mona to review using safe-outputs and create-pull-request. Do not write directly to main. If the sources do not justify an update, call noop with a short reason.

Check that the workflow configuration syntax is valid before finishing. Do not compile the workflow.

## Safe Outputs

- Use create-pull-request for the final pull request step.
- Use noop when no content update is needed.
