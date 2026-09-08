# Black Bag Security — Approved Page Design Archive

This directory is the preservation lock for page work approved during the 2026 redesign cycle.

## Purpose

Do not treat these files as loose design notes. They record the approved visual/implementation state and the exact artifact identities that must be preserved when the pages are integrated into the deployable site source.

The development repository deploys from `unattributed/blackbagsecurity.github.io` through `preview/source-ref.txt`; this archive branch deliberately does **not** change that deployment pointer.

## Approved pages

| Page | Status | Lock |
| --- | --- | --- |
| MAIN | Approved visual implementation; preserve unchanged while integrating | `main/APPROVAL_LOCK.md` |
| SERVICES | Approved visual implementation; preserve unchanged while integrating | `services/APPROVAL_LOCK.md` |
| CAPABILITY | **Explicitly approved for production** on 2026-09-08 | `capability/APPROVAL_LOCK.md` |
| ABOUT | Approved visual direction exists; exact-reproduction implementation still outstanding | not yet locked |

## Preservation rule

For MAIN, SERVICES, and CAPABILITY:

1. Preserve approved copy unless a later explicit approval supersedes it.
2. Preserve the approved imagery/crops and panel hierarchy.
3. Preserve the exact-reproduction workflow: reference → asset harvesting → measurement → implementation → browser review → correction → approval.
4. Do not replace approved page work with older operator-clarity layouts or generic components.
5. Before production promotion, compare the integrated page against the approved artifact and correct drift rather than reinterpret the design.

## Artifact integrity

The page-specific lock files contain SHA-256 hashes for the exact approved review artifacts and build packages. These hashes are the recovery/verification authority when moving the archived artifacts into normal source control.

Created from development repository base commit:

`53321d79f306807f5d2fe6fd77b96f735c63d2c8`

Preservation branch:

`archive/approved-pages-20260908`
