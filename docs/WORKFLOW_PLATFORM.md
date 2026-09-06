# Workflow maintenance

This repository owns organization defaults and a baseline starter template.
Reusable workflow implementation belongs to `septagon-dev/actions`.
The baseline caller and template pin its exact commit and provide explicit
required files. Product build, dependency and release checks belong in each
product repository; there is no private-module bootstrap template here.

The `workflow-platform-check.yml` workflow runs on pull requests and main
pushes. It installs Actionlint v1.7.12 with Go 1.26.2, lints workflows and the
baseline template, and validates template metadata with jq. Its tool binary
lives in the runner's temporary directory.

Run `actionlint`, `actionlint workflow-templates/*.yml` and `git diff --check`
locally. Run `jq empty workflow-templates/*.properties.json` for metadata and
`jq empty renovate.json renovate-config.json` if changing dependency policy.
Confirm the baseline's required paths exist before committing. These are local
checks; report remote CI and app activation separately.
