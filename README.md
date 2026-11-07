# HD2 Chef + MDL3 Coexist Pack

> **Status: permission pending.** This is an unofficial, modified build.
> We have asked the original authors for permission before any public
> distribution. Until they reply, this repository stays private and no
> release is published.

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
| Chef Shared Loader | 1.5.3 |
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
| Chef Shared Loader | Chefbo (Nexus 17760) |
| Chef Hand-off for MDL3 | JFRedist (Nexus 18398) |
| Official Simplified Chinese language pack | Nexus 17926 |
| Translation additions and pack assembly | liekong36 |

Permission requests have been sent to Chefbo and JFRedist. This repository
will remain private until both replies are received. If either author prefers
that the modified build is not distributed, it will be withdrawn immediately.

## Disclaimer

Unofficial, modified build; not affiliated with or endorsed by the original
authors. Provided as-is, at your own risk.

**Free and non-commercial.** No paywall, no paid access, no donations or ads
tied to this pack, and no commercial use of any kind.
