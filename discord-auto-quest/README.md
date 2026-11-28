# Orion — Discord Auto Quest Complete v4.10.11

> **Mirrored copy.** Author: **syntt_**. This repository does not own or maintain this script.

A console script that completes your Discord Quests automatically and renders a small dashboard inside the client.

> **Download:** [`Orion-Auto-Quest-v4.10.11`](https://github.com/0xHasan97/project-cheats/releases/tag/Orion-Auto-Quest-v4.10.11) — `Orion-Auto-Quest-v4.10.11.zip`.

## Package info

| Field | Value |
| --- | --- |
| Tool | Orion |
| Version | v4.10.11 |
| File | `orion-v4.10.11.txt` (JavaScript, paste into the DevTools console) |
| Size | 146,998 bytes · 2,519 lines |
| SHA-256 (txt) | `f8cfd729e5a8ead482aed44d15116e4da63a41fb7d4bef0b2e42890251352d83` |
| SHA-256 (zip) | `a16944cd9168c27e1e16cf79714ac0c9a16a0de865c727d191dde0a8ac307efc` |

## Requirements

- **Discord desktop app** — GAME and STREAM quests need the native client; a browser tab can only handle the other types.
- DevTools access (`Ctrl + Shift + I`). If the console refuses the paste, type `allow pasting` first.

## Usage

1. Open the Discord desktop app and press `Ctrl + Shift + I` to open DevTools.
2. Switch to the **Console** tab.
3. Paste the whole script and press Enter. The Orion panel appears in the top-right of the client.
4. Let it run. Watch the log; press **STOP** to end it, or **HIDE** (`Shift + .`) to collapse the panel.

## Quests it handles

| Type | What it does |
| --- | --- |
| `GAME` | Launches the quest's game/activity and reports progress (desktop only) |
| `STREAM` | Watches the required stream (desktop only) |
| `ACTIVITY` | Plays the quest activity |
| `WATCH_VIDEO` | Watches the quest video and claims it |
| `ACHIEVEMENT` | Runs the achievement bypass — see the note below |

## Panel options

| Option | Default | Meaning |
| --- | --- | --- |
| Auto-enroll | on | Enrolls in available quests before running them |
| Auto-claim | off | Claims rewards automatically instead of leaving CLAIM buttons |
| Play sound | off | Plays a short chime when a quest finishes |
| Random delay | off | Adds a 1–30 minute randomised gap between cycles |
| Hide activity | off | Turns Discord's `showCurrentGame` off while quests run, then restores it |

## Built-in limits

2,519 lines of quite defensive code. Useful to know before you run it: **25 min** hard abort per task · **90 s** heartbeat grace on GAME/STREAM · **3** retries on 429/5xx · abort after **5** consecutive failures · idle loop waits 4–6 s between rescans.

## About ACHIEVEMENT quests

These can't be faked from the client alone, so the script OAuth-authorises the quest's own app on your account, posts the achievement progress, then revokes the grant. It asks for consent first (Cancel, `Esc`, clicking the backdrop, or 60 s of inactivity all decline) and snapshots your existing grants beforehand so it never leaves an authorisation it can't undo. It can use an optional localhost relay at `127.0.0.1:43210` (`tools/orion-relay`, not included here), then falls back to a Vencord IPC plugin or a direct request.

## Warnings

- Automating quests and modifying the Discord client both break Discord's Terms of Service. **Account suspension is a real possibility.**
- Console code runs with full access to your session. Read the source before you paste it anywhere — that applies to this copy as much as any other.
- Reloading the tab (`Ctrl + R`) also stops it; if it ever seems stuck, that's the clean reset.

---

## Credits

- **syntt_** — author of Orion

For archival/mirroring purposes only. All rights belong to the original author.