# Changelog

All notable changes to the catalog (`catalog/catalog.toml` and `catalog/catalog.schema.json`). The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); the versions are [semantic](https://semver.org/spec/v2.0.0.html), and every release is an immutable tag `vMAJOR.MINOR.PATCH` on this repository.

## Policy

| Change | Release |
|---|---|
| A repository is added | minor |
| A repository is renamed or removed, or `catalog.version` changes (a breaking schema change) | major |
| An existing entry's purpose, contents, wave or layers change; an optional schema field is added; wording | patch |

- Every pull request that changes `catalog/catalog.toml` adds a line under **Unreleased**; `catalog.yml` fails the pull request otherwise.
- After the merge a maintainer runs `pub catalog sync`, which converges every repository's description, homepage, topics and the `ring`, `wave` and `layers` custom properties on GitHub from the new catalog.
- A release moves the **Unreleased** lines under a new version heading with the date and publishes the tag as an immutable release. Consumers pin a tag; `main` is not a contract.

## Unreleased

## v1.0.0 - 2026-09-03

### Added

- The initial catalog: every repository of the organization with its ring (spine, platform, system, domain, standards), layers, wave, purpose and planned contents, and the `[catalog]` table (`version = 1`, the organization, the site).
- `catalog.schema.json` (JSON Schema 2020-12), served at `https://publicsoftware.dev/catalog.schema.json`.
- `catalog.yml`: `pub catalog validate` on every pull request and in the merge queue, a seeded-violation check on the validator, the schema `$id` check and this changelog rule.
