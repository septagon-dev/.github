# Septagon Workflow Platform

Septagon repositories should consume reusable workflow building blocks from the public `.github` repository instead of re-implementing repository-local CI.

## Design Rules

1. Reuse central workflows before adding repo-local YAML.
2. Keep private module authentication in one place.
3. Standardize core Actions versions across repositories.
4. Treat baseline checks, Go validation, and release automation as separate workflow classes.

## Workflow Classes

### Baseline-only repositories

Use only the reusable repository baseline when the repository is documentation-first or intentionally empty during bootstrap.

Expected workflow:

- `.github/workflows/repository-baseline.yml`

### Go module repositories

Use the reusable Go CI workflow for Go libraries and runtime packages.

Expected workflow shape:

- baseline workflow
- repo-local workflow that calls `septagon-dev/.github/.github/workflows/reusable-go-ci.yml`

Required conventions:

- `actions/checkout@v6`
- `actions/setup-go@v6`
- `GOWORK=off` for split-repo validation
- central private-module auth through `SEPTAGON_MODULES_TOKEN`

### Application repositories

App repositories may keep repo-local smoke or release workflows, but they should still consume reusable pieces for:

- Go toolchain setup
- private module authentication
- baseline validation

## Private Module Policy

Private module access must flow through the reusable platform.

Do not duplicate this logic in repository-local workflows:

- `git config` token rewriting
- `GOPRIVATE` / `GONOSUMDB` / `GONOPROXY`
- `GOWORK=off`

Use the reusable Go workflow or the `setup-private-go` composite action instead.

## Current Standards

- Baseline checks live in `.github/workflows/reusable-repository-baseline.yml`
- Go CI lives in `.github/workflows/reusable-go-ci.yml`
- Private module bootstrap lives in `.github/actions/setup-private-go/action.yml`
- Workflow templates in `workflow-templates/` should point to reusable workflows instead of embedding custom CI logic
