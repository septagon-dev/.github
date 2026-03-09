# Septagon GitHub Profile Guide

Last updated: 2026-03-09

## What GitHub actually gives you

GitHub organization profiles have four main public surfaces:

1. profile fields: description, location, website, email
2. organization profile picture
3. public organization profile README
4. pinned repositories

GitHub documents these directly:

- organization profile overview: https://docs.github.com/en/account-and-profile/concepts/organization-profile
- custom organization profile README and pinned repositories: https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/customizing-your-organizations-profile
- verified domain badge: https://docs.github.com/en/organizations/managing-organization-settings/verifying-or-approving-a-domain-for-your-organization

## Evidence-based content recommendations

These are the recommendations that matter for the organization page.

### 1. Put the company explanation at the top in one line

Nielsen Norman Group recommends a tagline that succinctly states what the organization does at the top of the About page, followed by a meaningful summary in clear, plain language.

Source:
- https://media.nngroup.com/media/reports/free/Presenting_Company_Information_on_Corporate_Websites_3rd_Edition.pdf

### 2. Keep the summary short and scannable

NNGroup recommends:
- a tagline on the homepage
- 1 to 2 short scannable paragraphs at the top of the About page
- key facts made prominent and scannable

Source:
- https://media.nngroup.com/media/reports/free/Presenting_Company_Information_on_Corporate_Websites_3rd_Edition.pdf

### 3. Do not overload the page

Users scan web content rather than reading line by line. University of Illinois summarizes the underlying NNGroup findings this way: users read only about 28% of the words on a page, and concise, scannable, objective writing improves usability substantially.

Source:
- https://publish.illinois.edu/libraryweb/introduction/understanding-our-users/

### 4. Keep actions limited

Because users scan, the org page should not present a wall of links. A small number of clear next steps is stronger than trying to expose the whole ecosystem from the profile page.

This is an inference from:
- GitHub allowing pinned repositories for key destinations
- NNGroup guidance favoring scannable summaries and prominent key facts

## Septagon recommendation

Use this exact structure.

### Profile fields

- **Name:** `Septagon`
- **Description:** `Software products and operating layers for teams that care about leverage, boundaries, and execution quality.`
- **Website:** `https://septagon.dev`
- **Email:** `hello@septagon.dev`
- **Location:** only add if you want the org to look explicitly regional

### README shape

Keep the public README to:

1. company name
2. one-line tagline
3. one short paragraph
4. one short flagship paragraph
5. three start links
6. one closing line

That is why `SEPTAGON_ORG_PROFILE_README.md` is intentionally small.

### Pins

GitHub allows up to six pinned repositories. Do not use all six unless you actually need them.

Best initial set:

1. `platformkit`
2. `.github`
3. `platformkit-community`

If you add more later, do it only when they are independently real.

### Verified badge

Verify `septagon.dev` in the organization settings and keep the profile website and email on that domain so the verified badge can display correctly.

GitHub requirement:
- the website and email shown on the profile must match verified domain(s)

Source:
- https://docs.github.com/en/organizations/managing-organization-settings/verifying-or-approving-a-domain-for-your-organization
