# Septagon Repository Standards

This repository owns the GitHub organization defaults for `septagon-dev`.

## Why This Exists

GitHub supports three separate mechanisms that should not be conflated:

1. A public `.github` repository for organization profile content and default community health files.
2. Reusable workflows for centrally maintained CI logic.
3. Workflow templates for the GitHub UI when creating or adding workflows.

Septagon uses all three.

## What Lives Here

- organization profile README
- default `CONTRIBUTING`, `SECURITY`, `SUPPORT`, issue forms, and pull request template
- reusable workflows called by product repositories, including baseline, code-quality, and Go validation lanes
- workflow templates shown in GitHub's workflow UI

## What Does Not Live Here

- repository-specific starter files that should become part of each repository's history
- product source code
- private operational automation

That second class belongs in `repo-template`.
