# STOP win from WIN!

> 防微杜渐 (fáng wēi dù jiàn) — a classical Chinese idiom: "nip problems in the bud".
> 防win杜win swaps 微 (wēi) and 渐 (jiàn) for "win" — the meaning survives:
> nip Win-key mishaps in the bud, before they cost you the game.

---

"The moment the Start menu pops up, my run is over."

Late night. The boss at 1 HP, positioning perfect, one hit away from victory —
your left hand slips, and you press the Win key.
The Start menu covers half the screen. Your character falls at the monster's feet.
You stare at the screen, fuming, blood pressure maxed, mind blank.
You want to scream — nothing comes out. You want to retry — your hands won't move.

It's not your fault. It's the keyboard: `ctrl - win - alt - space - alt - fn - menu`.
The Win key sits right between Ctrl and Alt, waiting to backstab you.

![The moment](assets/win-press.png)

## What it does

| Key | Fate |
|---|---|
| Left Win | Retired. Pressing it does nothing — mash away mid-fight |
| Menu key | Resurrected as Right Win — on keyboards that have it, it's usually gathering dust |
| Right Alt | Promoted to Left Win — almost every keyboard has one, so even without a Menu key you still get a Win key |

## Install

1. Download `通用键盘布局.reg` (latest in [Releases](releases))
2. Right-click → Merge (or double-click), confirm "Yes" — admin rights required
3. Restart your computer

## Restore

1. Download `键盘布局恢复.reg`, double-click to import
2. Restart
3. Or: regedit → `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout` → delete the `Scancode Map` value → restart

## Why registry

- **System-level**: applies at the login screen and UAC prompts; read at boot, cannot fail to load
- **Zero background**: no process, no resident memory — there is nothing to kill
- **Anti-cheat friendly**: unlike AutoHotkey-style tools, there is no background process for anti-cheat to flag
- **No software needed**: nothing to install, double-click a .reg and reboot
- **Reversible**: one restore .reg brings everything back
- Works on Windows 7 / 8 / 10 / 11 (should — only tested on 10 and 11)

## Caveats

- **AltGr warning**: German, French, Spanish and other international layouts use Right Alt (AltGr) to type `@` `\` `€` — if you need AltGr, don't import this, or keep only the Menu key mapping
- Does not apply to RDP sessions (mapping happens at the local keyboard layer)
- Fn is hardware-level; no software can remap it
- Compact keyboards (65%/75%) have no Menu key — but you still get one Win key from Right Alt

## Alternatives?

PowerToys Keyboard Manager and AutoHotkey can remap keys too, but they work at the app layer: a resident background process, possible anti-cheat false positives, and no effect at the login screen. This is system-level, set-and-forget. Trade-offs: reboot required, global scope (can't limit to specific apps).

## License

🥚 [LICENSE](LICENSE)

> This release was made by my AI printer; the registry files, however, were written by me.
