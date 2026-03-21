# BB9900 wireless keyboard: ZMK config

This repository builds ZMK firmware for the **BB9900 BLE keyboard** and is now set up to be much friendlier for people who would rather edit a visual layout than hand-edit Devicetree syntax.

## The easiest way to customize this repo

Use **Nick Coutsos' Keymap Editor**:

- Editor: https://nickcoutsos.github.io/keymap-editor/
- Project README: https://github.com/nickcoutsos/keymap-editor

The editor can load ZMK keymaps from:

- a GitHub repository,
- the clipboard, or
- your local file system in Chromium-based browsers.

That makes it a great fit for this repo when you want to tweak layers, symbols, and behaviors without manually aligning bindings by hand.

If you want a repo-specific quick start, see [docs/keymap-editor-workflow.md](docs/keymap-editor-workflow.md).

## Recommended workflow

### Option A: edit directly from your GitHub fork

1. Fork this repository.
2. Open the Keymap Editor.
3. Choose the **GitHub** source.
4. Authorize GitHub access when prompted.
5. Open your fork of this repo.
6. Edit `config/bb9900.keymap` visually.
7. Save the changes back to the repository from the editor.
8. Download the firmware artifact from the GitHub Actions run that starts after your commit.
9. Unzip the artifact and flash `bb9900-zmk.uf2` to the keyboard.

### Option B: edit locally, then paste back into GitHub

1. Open `config/bb9900.keymap`.
2. Copy its contents.
3. In the Keymap Editor, choose the **Clipboard** source.
4. Paste the file contents into the editor.
5. Make your changes visually.
6. Copy the updated keymap back into `config/bb9900.keymap`.
7. Commit the change to your fork to trigger a firmware build.

## Important files

- `config/bb9900.keymap` is the **main keymap file** used by the build in this repository.
- `config/bb9900.conf` contains runtime options such as backlight, indicators, and trackpad tuning.
- `build.yaml` defines the GitHub Actions build matrix for this repo.
- `config/boards/bb9900/bb9900.keymap` is a board-scoped keymap copy that is useful for reference, but for normal customization you should edit `config/bb9900.keymap`.

If you only want to change what keys do, **start with `config/bb9900.keymap`**.

## What is already in the keymap

The default keymap includes:

- a base typing layer,
- a symbol layer,
- an upper/navigation layer,
- Bluetooth device selection,
- backlight controls,
- scroll controls,
- a tap dance for mouse click vs Bluetooth clear, and
- custom hold-tap behaviors.

Because these are standard ZMK concepts, the Keymap Editor can help with many of the common edits while still letting advanced users fine-tune the source directly.

## Build and flash

After you commit changes to your fork, GitHub Actions should build new firmware automatically.

1. Open the **Actions** tab in GitHub.
2. Open the latest workflow run.
3. Download the firmware artifact.
4. Extract the archive.
5. Flash `bb9900-zmk.uf2` to your keyboard.

For general flashing instructions, see the BB9900 firmware guide:

- https://github.com/ZitaoTech/BB9900-USB_BLE_Keyboard?tab=readme-ov-file#-how-to-update-the-firmware---

## Useful ZMK references

- Keycodes: https://zmk.dev/docs/codes
- Behaviors: https://zmk.dev/docs/behaviors

## Tips for non-developers

- Use the visual editor for key placement and layer changes.
- Use GitHub's web UI if you only need to replace `config/bb9900.keymap` with edited content.
- Keep commits small so it is easy to roll back to the last working layout.
- If something stops compiling, compare your changes against the previous version of `config/bb9900.keymap` first.

## Advanced note

Nick Coutsos' Keymap Editor keeps the `.keymap` source as the real source of truth, which means you can combine visual editing with direct ZMK source edits when you need features the UI does not expose cleanly.
