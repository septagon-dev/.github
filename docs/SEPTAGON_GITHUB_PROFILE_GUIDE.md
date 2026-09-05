# Maintaining the Septagon profile

[profile/README.md](../profile/README.md) is the source for the organization
README. Keep it short enough that a new reader can identify the company,
understand the current product and choose a useful next step.

Describe PlatformKit as the public Go reference architecture and PlatformKit
Mobile as its Expo and React Native client. Link both to `septagon-oss`.
Product setup and architecture details belong in those repositories. Remove
retired product links and unsupported feature claims when the source changes;
do not replace them with an internal repository inventory.

The company website is `https://septagon.dev`, and the contact address used
by this repository's community documents is `hello@septagon.dev`. Keep those
documents and the profile consistent. Brand images are in `assets/brand/`;
review the existing asset before replacing it.

Organization profile fields, the avatar, repository pins and domain
verification are managed through GitHub settings. A commit to the profile
README does not apply those settings. When a settings change is requested,
review the public profile and choose destinations that visitors can access.
The source tree does not establish the current settings or verification state.

Before committing a profile change, review the rendered Markdown, follow its
product links and run `git diff --check`. Keep private repositories, client
names, deployment details and unverified launch destinations out of the public
profile.
