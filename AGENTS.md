# Working in this repository

Read [README.md](README.md) for ownership and
[docs/WORKFLOW_PLATFORM.md](docs/WORKFLOW_PLATFORM.md) for the workflow files
and checks. This is an organization-profile and defaults repository, not a Go
or Node application. Product build commands belong in product repositories.

Keep the profile, support paths, contribution guide and issue contact links
consistent. Explain current behavior in prose and link to the source that owns
details. Do not restore split-repository migration instructions or require
obsolete workspace paths. Public documents must not disclose private catalog,
client, credential or deployment information.

For workflow changes, inspect the exact referenced shared contract in
`septagon-dev/actions`. Do not copy reusable implementations here or restore
split-repository bootstrap templates. Product CI belongs with product source.

Before committing, run git diff --check, review changed local links and URLs,
and run actionlint plus actionlint workflow-templates/*.yml. Validate template
metadata with jq empty and check the baseline's required paths. Validate edited
issue forms as YAML and edited Renovate files as JSON. These checks establish
local validity; they do not establish remote CI results or app activation.

Keep one logical change in one repository per commit, use a conventional
subject, and record real validation results. State failures and checks not run.
CLAUDE-facing instructions, if added, should point here rather than duplicate
these rules.
