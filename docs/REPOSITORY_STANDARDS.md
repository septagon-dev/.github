# Repository standards

This repository owns the `septagon-dev` organization profile, default community
documents, issue forms, workflow templates and Renovate preset. Product code
and its documentation belong in the repository that implements the behavior.
A README should tell a new reader what the repository owns, how to use it and
how to verify a change without requiring an old workspace layout.

Use each repository's current README, agent instructions and build files as
the authority for local commands. PlatformKit documents `make check`; its
mobile client documents `npm run check`. A documentation repository may have
only link, format and workflow checks. Do not require every repository to
invent a `make precommit`, `REPO_CHARTER.md` or migration document merely to
match a generic template.

Shared workflow implementation lives in `septagon-dev/actions`. The baseline
caller and starter template reference an immutable commit there. Configure the
required files to match the adopting repository. Product CI should execute that
repository's actual verification command and dependency contract. See
[WORKFLOW_PLATFORM.md](WORKFLOW_PLATFORM.md) for current checks.

A file-existence baseline establishes that files exist; it does not establish
that their contents are accurate or that the product works.

Keep public navigation focused on the public products and their source-owned
guides. Private catalog capabilities, client identities, credentials and
cluster details belong in their owning private repositories. Do not publish
an internal repository inventory as an organization profile.
