# Septagon organization defaults

This is the `.github` repository for `septagon-dev`.
[profile/README.md](profile/README.md) is the organization landing page.
The root contribution, conduct, security, support and pull-request files,
together with `ISSUE_TEMPLATE/`, provide community defaults for repositories
that do not supply their own.

This repository also holds workflow templates, a Renovate preset, and workflow
maintenance documentation. Its own baseline and the templates call shared
workflows in `septagon-dev/actions`. Reusable workflow and action files also
remain under `.github/` here; read the actual caller's `uses:` reference
before choosing which repository owns a workflow change.

For the current public product, start with
[PlatformKit](https://github.com/septagon-oss/platformkit) and
[PlatformKit Mobile](https://github.com/septagon-oss/platformkit-mobile).
Product architecture, setup and verification belong with their source.
Organization documentation should not reproduce private client, catalog or
deployment inventories.

Read [AGENTS.md](AGENTS.md) before editing. The
[repository standards](docs/REPOSITORY_STANDARDS.md) explain ownership;
[workflow documentation](docs/WORKFLOW_PLATFORM.md) describes callers and
checks. The [Renovate guide](docs/RENOVATE_ROLLOUT.md) separates committed
configuration from app activation, and the
[profile guide](docs/SEPTAGON_GITHUB_PROFILE_GUIDE.md) describes profile upkeep.

There is no Go module, npm project or Makefile here. Run `git diff --check`
and review changed links. Workflow maintenance also requires `actionlint`,
`actionlint workflow-templates/*.yml`, and JSON validation of the template
metadata, matching `.github/workflows/workflow-platform-check.yml`.
