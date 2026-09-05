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

Shared workflows live in `septagon-dev/actions`. This repository's baseline
and workflow templates reference that repository explicitly. Copies of reusable
workflows and a private-Go setup action also exist under `.github/` here;
their presence does not prove that a product uses them. Find a caller's
`uses:` reference and inputs before changing shared behavior. See
[WORKFLOW_PLATFORM.md](WORKFLOW_PLATFORM.md) for the current files and checks.

A workflow template is a starting point for a caller. Configure required files,
validation commands, permissions and private-module access to match that
repository. In particular, the baseline template's default file list and the
Go template's `make precommit` command need review before adoption. Passing a
file-existence baseline establishes that the files exist; it does not establish
that documentation is accurate or that the product works.

Keep public navigation focused on the public products and their source-owned
guides. Private catalog capabilities, client identities, credentials and
cluster details belong in their owning private repositories. Do not publish
an internal repository inventory as an organization profile.
