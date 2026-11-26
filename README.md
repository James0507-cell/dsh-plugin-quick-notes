# Quick Notes — a data-only DSH Mobile plugin

Quick Notes is a sample **declarative plugin pack** for DSH Mobile. A pack is one JSON file of data;
the app interprets it with its own renderer and never executes code from it.

This is the sample used for the **import from a local file** flow.

## What it adds

- A non-docked **Notes** page that explains the import steps and adds two actions (open Sessions,
  show a toast).
- A **QUICK NOTES** card on the Now screen with a button that opens the Notes page.
- A **NOTE** composer chip that inserts:
  `Save a one-line note: `
- Nothing else: no Settings section and no palette, so the page/card/chip trio is easy to compare
  with the richer Focus Timer sample.

## Get the file onto the phone

The plugin is exactly one file: `dsh-plugin.json` from this repository. Two ways to get it onto the
device:

1. **Download it from GitHub (recommended).** Open
   <https://github.com/James0507-cell/dsh-plugin-quick-notes>, tap `dsh-plugin.json`, then
   **Download raw file**. The file lands in the phone's **Downloads** folder. The direct raw URL is
   <https://raw.githubusercontent.com/James0507-cell/dsh-plugin-quick-notes/main/dsh-plugin.json>.
2. **Copy it over USB.** Connect the phone to a computer, copy `dsh-plugin.json` into a folder the
   phone can browse (for example **Downloads**), then eject the phone safely.

Renaming the file is harmless — the app installs it under its declared id
(`sample.quick-notes.json`) — but it must stay `.json`.

## Install from file

1. Open the app and go to **Settings -> Plugins**.
2. Tap **INSTALL PLUGIN**.
3. Choose **FROM FILE**.
4. Pick the downloaded `dsh-plugin.json` with the system file picker.
5. Check the preview (id `sample.quick-notes`, name "Quick Notes", version `1.0.0`) and confirm.

The installed pack is enabled by default and can be disabled, updated by importing a newer file, or
removed from the plugin manager at any time.

## Keep the file valid

- The document must stay **under 64 KiB** (the app refuses bigger files) and be valid UTF-8 JSON.
- Unknown fields are **refused**, not ignored, so a misspelled key fails the install with an error
  instead of being silently dropped.
- Only the declarative vocabulary is allowed: pages, home cards, Settings sections, composer chips
  and accent-only themes, with actions from `open-screen`, `open-page`, `toast`,
  `set-plugin-enabled` and `set-config`.
- It is data only: no code, no network access, no storage of its own; notes you type stay in the chat
  session. The pack itself stores nothing.

## Files

- `dsh-plugin.json` — the whole plugin (schema `apiVersion` 1).
- `README.md` — this file.
- `LICENSE` — MIT.

The plugin id `sample.quick-notes` is reserved by this repository; use a different vendor/name for
your own pack.
