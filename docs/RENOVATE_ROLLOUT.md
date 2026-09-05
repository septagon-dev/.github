# Renovate configuration and activation

[renovate-config.json](../renovate-config.json) is the organization preset.
[renovate.json](../renovate.json) opts this repository into
`local>septagon-dev/.github:renovate-config`. Those files configure Renovate;
they do not establish that the GitHub App is installed or running.

The preset declares a seven-day minimum release age, a Monday update schedule,
GitHub Actions digest pinning, a dependency dashboard and vulnerability alerts.
Major updates require dashboard approval. It groups non-major Actions updates
and disables automerge for the listed container, action and infrastructure
managers. Read the JSON for exact limits and package rules.

## Activate and verify

An organization maintainer chooses the app's repository access and a current
pilot set. Use active repositories with functioning checks, including this
repository if its shared preset is part of the pilot. Do not derive the pilot
from an archived workspace inventory.

Confirm that each repository's onboarding configuration extends the preset
and that its actual CI requirements protect dependency updates. Keep automerge
disabled during the pilot. Inspect the dashboard and proposed updates to
confirm digest pins, the age and schedule rules, major-update approval and
vulnerability-alert handling in the installed Renovate version.

This repository still has Dependabot version updates configured in
`.github/dependabot.yml`. Disable overlapping version updates only after
Renovate is observed working; keep security alerts available. Expanding app
access, merging onboarding changes and changing organization settings are
operational actions, not effects of editing this guide.

To stop the rollout, suspend the app or narrow its repository access and review
open dependency pull requests. Keep the preset and security-alert configuration
available while investigating. Locally, `jq empty renovate.json
renovate-config.json` checks JSON syntax only.
