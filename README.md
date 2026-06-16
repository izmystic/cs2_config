# cs2_config

Personal Counter-Strike 2 config. Includes a subtick jump workaround, a jump mode toggle for workshop vs. live play, and a rainbow HUD cycling alias.

## Installation

Copy all three files into your CS2 cfg folder:

```
steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg\
```

CS2 will load `autoexec.cfg` automatically on launch. Run `exec autoexec` in console to reload at any time (aliased as `eae`).

## Files

| File | Purpose |
|------|---------|
| `autoexec.cfg` | Main config - binds, aliases, viewmodel, radar |
| `workaround_jump_start.cfg` | Subtick jump press handler |
| `workaround_jump_end.cfg` | Subtick jump release handler |

## Binds

| Key | Action |
|-----|--------|
| `WASD` | Movement (also cycles HUD color in workaround mode) |
| `Space` / `Scroll Down` | Jump (mode-dependent, see below) |
| `Ctrl` | Duck |
| `Shift` | Sprint |
| `1–5` | Weapon slots |
| `8` / `9` | Inventory next / prev |
| `Left/Right Arrow` | Turn left / right |
| `Up Arrow` | Instant 180 turn right |
| `Down Arrow` | Instant 180 turn left |
| `F5` | Toggle jump mode |

## Jump Mode Toggle (F5)

Two modes, swapped with `F5`:

- **Workaround mode** (default) - uses the subtick jump workaround via `+jump_` alias. HUD cycles through rainbow colors on movement.
- **Workshop mode** - uses standard `+jump`. HUD is set to white (color 1) and stays frozen.

The workaround fires `workaround_jump_start.cfg` on keydown and `workaround_jump_end.cfg` on keyup, toggling the `jump` convar through specific values (`1 → 0 → 0` / `-999 → 0 → 0`) to produce consistent jump height under CS2's subtick system.
