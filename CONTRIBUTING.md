# Contributing

This default guide applies to repositories in `septagon-dev` that do not
provide their own contribution guide. Start with the target repository's
README and agent instructions. They define its ownership, setup and required
checks; shared defaults do not replace its implemented workflow.

Keep changes focused on a behavior and its owner. Write clear prose and code
using the capability's domain language, and make inputs, decisions and effects
visible. Update documentation when the behavior it describes changes. Remove
replaced instructions and implementations instead of keeping competing paths.

A pull request should explain the problem, the resulting behavior, why the
change belongs in that repository, and the checks actually executed. Include
relevant failures or untested behavior. Use conventional commit subjects and
keep one logical change in one repository per commit.

For this organization-profile repository, read [AGENTS.md](AGENTS.md), review
changed links and run `git diff --check`. Workflow and template changes also
follow the checks in [WORKFLOW_PLATFORM.md](docs/WORKFLOW_PLATFORM.md). There
is no application build or repository-wide `make precommit` target here.

Keep secrets, client information and private deployment details out of public
issues, documents and examples. Report vulnerabilities privately through
[SECURITY.md](SECURITY.md). Participation follows the
[Code of Conduct](CODE_OF_CONDUCT.md).
