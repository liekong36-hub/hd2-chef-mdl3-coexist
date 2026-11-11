# HD2 Chef + MDL3 Coexist Pack

[English](README.md) · [简体中文](README.zh-CN.md)

> **Status: both upstream authors have permitted this modified build, with
> conditions.** It stays online only until one of the official routes below
> works: Quick Deploy's helper covering MDL3, or MDL3 running under Chef.
> This is an **unofficial, modified build**. Report problems with the pack to
> liekong36; forward to the upstream authors only issues that also reproduce
> on their unmodified release. The pack will be taken down once either route works.

A free, non-commercial compatibility pack for **Helldivers 2** that lets
**Chef Shared Loader** and **MDL3** run side by side under
**HD2 Mod Quick Deploy**.

## Why

HD2 Mod Quick Deploy deploys only one loader at a time. With MDL3 selected,
Chef Shared Loader is excluded entirely and never starts — its F9 options
menu and every Chef addon become unavailable. This pack makes the manager
treat Chef as an ordinary mod while MDL3 remains the selected loader.

## How it works

- MDL3 stays a **separate loader entry**, always deployed last (highest patch, owns the boot script).
- Chef sits below it; `Chef Hand-off for MDL3` starts Chef about 6 seconds after launch.
- The pack contributes two patch layers: Chef core and the hand-off addon. **No language packs are distributed**; users who want a translated menu can install their own `-- HD2-Lang` data-only packs separately, and Chef merges same-named languages automatically.
- Chef's core resource is renamed so the manager no longer identifies it as a loader.
- A small runtime compatibility step in the core repairs addons that MDL3 started before the hand-off.
- Plain Lua only: no gameplay code, no anti-cheat behaviour; the manager adds patch layers without modifying base game files.

## Compatibility

| Component | Version |
| --- | --- |
| Game | Helldivers 2 (current build) |
| MDL3 | 3.0.0-dev.33 – 3.0.0-dev.52 (tested on dev.33, dev.36, dev.47 and dev.52) |
| Chef Shared Loader | 1.5.4 (core resource renamed) |
| Chef Hand-off for MDL3 | 0.2.6, modified as 0.2.6-lk36.1 |
| Mod manager | HD2 Mod Quick Deploy 0.17.0 |
| Language packs | Not included in this build |

MDL3 is **not** included in this pack. Upgrading or rolling back MDL3 does
not require changing the pack.

## Install / update

1. Add the pack, or use **Replace** on the existing entry (Replace keeps load order, enabled state and options).
2. Confirm MDL3 is still the selected loader.
3. Deploy once, then start the game from Steam.
4. Press F9; expand a mod with `→` to see its settings.

Release artifacts (the pack zip, with a checksum) are attached to GitHub
Releases; the zip is not committed to the repository itself.

## Credits and permissions

| Work | Author |
| --- | --- |
| Chef Shared Loader | Th3chef (`github.com/Th3chef/Chef-Shared-Loader`), Chefbo on Nexus (17760) |
| Chef Hand-off for MDL3 0.2.6 | JFRedist (`github.com/JFRedist/HD2-Chef-Handoff-for-MDL3`, Nexus 18398) |
| Simplified Chinese packs | Not redistributed (third-party, see below) |
| Translation additions and pack assembly | liekong36 |

The hand-off addon is used under the MIT license (Copyright (c) 2026
JFRedist); its unmodified license text ships as `LICENSE-HANDOFF` in the pack.
Our build carries its own version (`0.2.6-lk36.1`) and an identifying `from`
string so its logs cannot be mistaken for the upstream release.

**Please report problems with this pack to liekong36, not to the upstream authors.**

Th3chef (Chefbo) has reviewed the diff and permitted the pack to stay up under
the conditions above. He also confirmed the dead-module case originates on
MDL3's side: dev.36 starts addons declaring `chef-shared-loader` before the
hand-off, and the MDL3 author is restoring the rule that MDL3 never starts
those. Once that lands, our runtime rewrite in the core is no longer needed.

## Disclaimer

Unofficial, modified build; not affiliated with or endorsed by the original
authors. Provided as-is, at your own risk.

**Free and non-commercial.** No paywall, no paid access, no donations or ads
tied to this pack, and no commercial use of any kind.

## Scope and limitations

- This pack is **for dual-loader setups only** (Chef + MDL3 together).
- If you only want Chef without MDL3, use the official unmodified Chef Shared
  Loader release. Quick Deploy recognises it as a loader via its hard-coded
  resource IDs; our renamed build is deliberately invisible to that check and
  cannot be chosen as a loader.
- Do not enable the official Chef entry and this pack at the same time.
- The Simplified Chinese language packs work on their own and can be installed
  separately in either setup.

## Language files

No language files are bundled with this pack. The upstream Simplified Chinese
language pack (Nexus 17926, by MCTimeRL) explicitly forbids reuploading it to
other sites, so we do not include it, and we do not include our own translation
additions either. Install language packs separately if you need them.
