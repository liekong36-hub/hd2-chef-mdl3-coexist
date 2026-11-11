# Changelog

[English](CHANGELOG.md) · [简体中文](CHANGELOG.zh-CN.md)

> Note: since v1.3 the public release contains **no language packs**.
> Translation-related entries in v1.0 - v1.2 are historical context, not part
> of the current package. Experiments that were reverted are not listed.

## v1.0 - 2026-11-05 (first release)

- MDL3 stays on the highest patch, Chef sits below it, and the hand-off addon starts Chef about 6 seconds after launch, so both loaders coexist.
- Chef's core resource is renamed so the manager no longer classifies it as a loader and excludes it.
- Chef's core and the hand-off addon are bundled into one manager entry, so deploying no longer needs a manual script.
- The patch bundle format was worked out and a data-only language pack mechanism was established for later translations.

## v1.1 - 2026-11-07 (upgrade and distribution)

- The core is upgraded to Chef Shared Loader 1.5.3, with the core rename and the built-in compatibility step migrated.
- The manifest Guid and name are kept unchanged, so the manager's Replace updates the pack without losing load order or switches.
- Compatibility with MDL3 3.0.0-dev.33 - dev.52 is established and tested on dev.33, dev.36, dev.47 and dev.52.

## v1.2 - 2026-11-07 (hand-off reworked under upstream permission)

- The hand-off addon is rebuilt on JFRedist's official 0.2.6 release, with its own version string and identifying log text.
- The unmodified MIT license and copyright line are shipped with the pack, together with an unofficial-build notice, an upstream link and a clear bug-report owner.

## v1.3 - 2026-11-08 (public release)

- The public release keeps only two patch layers (Chef core and hand-off addon); all Chinese language packs, both third-party and our own, are removed.
- Bilingual project documentation is added, explaining that language packs must be installed separately and that same-named languages merge automatically.
- The release is clearly marked as an unofficial modified build, with bug reports routed to liekong36 and a take-down condition once either official compatibility route works.

## v1.4 - 2026-11-11

- Core upgraded to Chef Shared Loader 1.5.4, with the core_2 rename and the built-in compatibility step migrated; compatible with MDL3 dev.33 - dev.52.
