# Workflow maintenance

This repository provides organization defaults and workflow templates. Its
active baseline and both templates call workflows in `septagon-dev/actions`.
The exact `uses:` reference in a caller determines which implementation runs;
a similarly named file in this repository is a separate file.

## Files and ownership

`.github/workflows/repository-baseline.yml` calls the shared repository
baseline with an explicit list of this repository's required community and
profile files. That list is the check's contract. It does not require a Go
module or an application build.

`.github/workflows/workflow-platform-check.yml` runs when workflow/action
files, templates or the repository/workflow standards change. It installs
actionlint v1.7.8, lints repository workflows and templates, and validates each
template's JSON metadata. This is the locally reproducible workflow check.

`workflow-templates/septagon-baseline.yml` calls the shared baseline and
dependency review. `workflow-templates/septagon-go-ci.yml` adds CodeQL and Go
validation, currently requesting private modules, `make precommit` and a
`SEPTAGON_MODULES_TOKEN` secret. Review those choices for each caller:
public modules do not need a private token, and the validation command must
exist in the consuming repository.

Reusable baseline, Go, CodeQL and dependency-review workflows, plus
`.github/actions/setup-private-go/action.yml`, are also present here.
The shared `actions` repository additionally has Node and Helm workflows.
Do not edit a local copy expecting a caller of `septagon-dev/actions` to
change. Inspect the referenced implementation and its inputs first.

## Configure a caller

Keep toolchain setup, private-module authentication and common validation in
the shared workflow where the caller already uses it. Supply the consuming
repository's real check command through the workflow's inputs. A reusable
workflow's default command is not a promise that the target repository defines
that command.

The private-Go setup action writes Go privacy settings, `GOWORK=off` and a
Git URL rewrite for module access. Enable it only for callers that need
private dependencies and pass the token through the declared secret input.
Do not copy credential values into workflow files, documentation or logs.

Keep product-specific journeys and release behavior with the product.
Documentation changes should describe the workflows that exist; changing
workflow ownership or organization settings is separate operational work.

## Validate this repository

Run from the repository root with actionlint and jq installed:

```sh
git diff --check
actionlint
actionlint workflow-templates/*.yml
for file in workflow-templates/*.properties.json; do
  jq empty "$file"
done
```

Also confirm that every path listed in
`.github/workflows/repository-baseline.yml` exists. When editing Renovate
configuration, run `jq empty renovate.json renovate-config.json`; this checks
JSON syntax, not Renovate's schema or app activation. Review changed Markdown
links and describe exactly which checks passed. No local check here proves
that a workflow executed successfully on GitHub or that an organization app
is installed.
