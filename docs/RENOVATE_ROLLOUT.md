# Renovate rollout

The organization policy lives in `renovate-config.json` at the repository root.
Renovate automatically proposes this preset when a `septagon-dev` repository is
onboarded. The preset pins GitHub Actions to immutable digests, waits seven days
before routine upgrades, keeps security remediation immediate, and requires a
human decision for major upgrades.

## Activation

Activation changes GitHub organization state and is intentionally separate from
this repository change:

1. Install the Mend Renovate GitHub App for the `septagon-dev` organization. Start
   with the managed first-class repositories in `infrastructure/infra/catalog/`;
   include `.github`, `actions`, and `platformkit-infra` in the pilot.
2. Confirm the onboarding pull request in each pilot repository extends
   `local>septagon-dev/.github:renovate-config`.
3. Require the repository's real CI checks before merging any dependency update.
   Do not enable automerge during the pilot.
4. Verify that the Dependency Dashboard exists, GitHub Actions references remain
   full-length SHA pins with version comments, and vulnerability-alert pull
   requests are not held by the normal weekly schedule.
5. Expand installation to every managed first-class repository after one clean
   weekly cycle. Keep Dependabot security updates enabled; disable overlapping
   Dependabot *version* updates only after Renovate is demonstrably active.

## Rollback

Suspend the app or restrict its repository access. Existing dependency pull
requests can be closed without changing application code. Keep the shared preset
and Dependabot security alerts in place while investigating.
