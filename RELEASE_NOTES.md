# Release notes — v1.4

> **Ready to publish.** Both JFRedist and Th3chef / Chefbo have permitted
> this modified build. Conditions: keep it clearly marked as an unofficial
> modified build; keep bug reports for the pack with liekong36 and forward only
> issues that also reproduce on the upstream release; take the pack down as
> soon as one of the official compatibility routes works.

## Highlights

- Chef Shared Loader core updated to **1.5.4**; hand-off based on official **0.2.6** with its own `0.2.6-lk36.1` version.
- **No language packs are bundled.** The public release contains only the Chef core and the hand-off addon; install `-- HD2-Lang` packs separately if needed.
- Hand-off is the official 0.2.6 (its own `0.2.6-lk36.1` version); our earlier "retry every unfinished hand-off" change was removed at the author's request.
- Compatible with MDL3 3.0.0-dev.33 – 3.0.0-dev.52; tested on dev.33, dev.36, dev.47 and dev.52.
- Manifest Guid and Name unchanged, so the pack can be updated with the manager's Replace.

## Install / update

1. Use **Replace** on the existing pack entry (keeps load order, enabled state and options), or Add for a fresh install.
2. Keep MDL3 as the selected loader.
3. Deploy once, then launch the game from Steam. Press F9 to open the menu.

## Package

Attach `Chef MDL3 Coexist Pack 1.4 (WorkBuddy).zip` to the release.
MD5: `3756169aa7661f4c6d2835a91a63a3ff` — re-check before attaching, since the zip changes whenever the pack is rebuilt.

## Disclaimer

Unofficial, modified build; not affiliated with or endorsed by the original authors.
Free and non-commercial: no paywall, paid access, donations, ads or commercial use.
This pack will be taken down once Quick Deploy's helper covers MDL3, or once
MDL3 runs under Chef.
