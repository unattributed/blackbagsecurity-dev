# Black Bag Security Development Preview

This repository is the deployment control plane for the Black Bag Security website redesign preview.

It does **not** contain the production website source. The authoritative website source remains in [`unattributed/blackbagsecurity.github.io`](https://github.com/unattributed/blackbagsecurity.github.io).

## Purpose

- publish the redesign to `https://dev.blackbagsecurity.com`
- keep production `www.blackbagsecurity.com` isolated from design work
- make each preview reproducible from a named source branch or commit
- preserve a clean VCS promotion path from feature work to the redesign integration branch and finally to production

## Source model

The preview workflow reads `preview/source-ref.txt` and checks out that ref from:

`unattributed/blackbagsecurity.github.io`

During active homepage implementation this may point to `feature/homepage`. For integrated review it should point to `redesign/v2`. It can also be pinned to a commit SHA for a deterministic review build.

## Deployment

GitHub Pages is deployed with GitHub Actions using the official GitHub Pages actions. The workflow:

1. checks out this deployment repository
2. reads the configured website source ref
3. checks out the authoritative website repository at that ref
4. overrides the Jekyll site URL for the development hostname
5. builds the existing `docs/` Jekyll site
6. removes production-domain deployment metadata from the artifact
7. injects development `noindex, nofollow, noarchive` directives
8. writes a restrictive development `robots.txt`
9. uploads and deploys the Pages artifact

## Security and data handling

The development site is public infrastructure. Never place client data, engagement evidence, credentials, tokens, secrets, private keys, confidential reports, or restricted information in this repository or in website source intended for preview deployment.

The preview is intentionally marked for search-engine exclusion, but this is not an access-control mechanism.

## Production boundary

- `unattributed/blackbagsecurity.github.io:main` remains production
- `unattributed/blackbagsecurity.github.io:redesign/v2` is the redesign integration branch
- focused `feature/*` branches are used for implementation
- this repository exists only to build and publish development previews

Production promotion remains an explicit reviewed VCS action.
