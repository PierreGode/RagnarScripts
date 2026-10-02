# RagnarScripts

A shared library of scripts you can install into [Ragnar](https://github.com/PierreGode/Ragnar)
straight from the dashboard.

Clone this repo next to (or anywhere reachable by) your Ragnar install and
Ragnar will discover it automatically. Then use the **Install from RagnarScripts**
section on the relevant card to copy a script into your unit's local library.

## Layout

| Folder | Contents | Installs into Ragnar as |
|---|---|---|
| [`rubber-ducky/`](rubber-ducky/) | USB HID keystroke-injection payloads (`.ducky` / `.txt`) | `files/rubber-ducky/` (Pentest → Rubber Ducky card) |
| [`console-scripts/`](console-scripts/) | Serial-console command sequences (`.json`) | `data/console_scripts/` (Dashboard → Device Console card) |

## How Ragnar finds this repo

Ragnar looks, in order, for:

1. `$RAGNAR_SCRIPTS_DIR` (if set)
2. a `RagnarScripts` folder next to the Ragnar repo
3. `~/RagnarScripts`
4. `/home/pi/RagnarScripts` or `/home/ragnar/RagnarScripts`

The first one that exists wins. Set `RAGNAR_SCRIPTS_DIR` if you keep it elsewhere.

## Adding your own

Drop a new file into the matching folder and push. Installing never deletes or
overwrites your hand-made scripts in Ragnar unless they share a filename — the
local `files/rubber-ducky/` and `data/console_scripts/` folders stay fully
editable, so you can still create and upload your own directly in the dashboard.

- **Ducky payloads** use the official Ducky syntax (`STRING`, `ENTER`, `GUI r`,
  `DELAY`, …) or Ragnar's plain-text form (`type:`, `press:`, `wait:`, `key:`).
  The first `REM`/`#` line is shown as the description.
- **Console scripts** are JSON: `{ "name", "description", "vendor", "commands":
  [ {"cmd": "...", "delay": 1.0}, ... ] }`. The **file name is the script id**
  (letters, digits, `_`, `-`).

Authorized testing only.
