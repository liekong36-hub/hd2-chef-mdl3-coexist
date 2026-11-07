# Troubleshooting

Classify the symptom before changing any files:

- **A. The mod is missing from F9** → manager / deployment issue.
- **B. It appears by name but has no settings and does nothing** → loader pre-emption, handled automatically by this pack.
- **C. Settings are there but nothing shows in game** → the mod's own trigger conditions or options.

## Check in order

1. In the manager: is the entry enabled, and are its `files` non-empty? Empty files with `loader=true` mean it was classified as a loader and excluded — usually a second, unmodified Chef core has been enabled.
2. `chef_handoff.log`: is the addon `managed` or `load failed` in MDL3's modules table?
3. MDL3's own log: `FATAL: Chef Shared Loader without camera, call, ...` means MDL3 started the addon before the hand-off.
4. `chef_loader.log`: `started <mod>` with a long-term `0.000 ms` status means `install()` never ran; `failed to run:` or `could not compile` gives the error text directly.
5. The mod's own `own_log` file: missing, or `FATAL: no engine` / `no update hook`.
6. `chef_loader_lang_missing.txt` affects translations only, not functionality.

Log files live in the game's user data folder (`%APPDATA%\Arrowhead\Helldivers2`); MDL3's own log is under its local data folder.

## Common false alarms

- Many in-world markers are hidden on the ship — enter a mission.
- The F9 menu is folded: `→` expands, `>` changes a value, `DEL` restores a default, `←` folds.
- Category master switches can be off.
- Some mods require a specific game build or Chef version.

## If a new mod still fails (class B)

The pack's Chef core applies two small runtime source rewrites to addons that
declare `chef-shared-loader` as a requirement: it disables a stale
"already loaded" guard and replaces a plain `type(chef)` check with a
Chef-API feature check. A mod written differently may not match those two
patterns. In that case, share the mod's first ~30 lines plus the FATAL line
from MDL3's log; a further compatibility rule can be added to the pack core.
The mod file on disk does not need to be edited.
