# HD2 Chef + MDL3 Coexist Pack

> **Status: permission partly granted.** JFRedist has permitted a modified
> build of his hand-off addon under conditions that are implemented here.
> Permission from Th3chef for the Chef Shared Loader core is still pending.
> This repository stays **private** and no release is published until then.

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
- The pack contributes four patch layers: Chef core, hand-off addon, official Simplified Chinese pack, extra translation pack.
- Chef's core resource is renamed so the manager no longer identifies it as a loader.
- A small runtime compatibility step in the core repairs addons that MDL3 started before the hand-off.
- Plain Lua only: no gameplay code, no anti-cheat behaviour; the manager adds patch layers without modifying base game files.

## Compatibility

| Component | Version |
| --- | --- |
| Game | Helldivers 2 (current build) |
| MDL3 | 3.0.0-dev.36 – 3.0.0-dev.43 (tested on dev.36) |
| Chef Shared Loader | 1.5.3 (core resource renamed) |
| Chef Hand-off for MDL3 | 0.2.6, modified as 0.2.6-lk36.1 |
| Mod manager | HD2 Mod Quick Deploy 0.17.0 |
| Menu language | Simplified Chinese, 508+ texts |

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
| Official Simplified Chinese language pack | Nexus 17926 |
| Translation additions and pack assembly | liekong36 |

The hand-off addon is used under the MIT license (Copyright (c) 2026
JFRedist); its unmodified license text ships as `LICENSE-HANDOFF` in the pack.
Our build carries its own version (`0.2.6-lk36.1`) and an identifying `from`
string so its logs cannot be mistaken for the upstream release.

**Please report problems with this pack to liekong36, not to the upstream authors.**

A permission request has been sent to Th3chef for the Chef Shared Loader core
and translations. This repository stays private until that reply arrives; if
permission is declined, the pack will be withdrawn immediately.

## Disclaimer

Unofficial, modified build; not affiliated with or endorsed by the original
authors. Provided as-is, at your own risk.

**Free and non-commercial.** No paywall, no paid access, no donations or ads
tied to this pack, and no commercial use of any kind.
