# BB9900 Keymap Editor workflow

This short guide explains the most user-friendly way to edit this repository with the Nick Coutsos Keymap Editor.

## Use this file

When the editor asks which keymap to open, use:

- `config/bb9900.keymap`

That is the main file customized by this repository's GitHub Actions build.

## Best workflow for most users

1. Fork this repository.
2. Open https://nickcoutsos.github.io/keymap-editor/.
3. Choose **GitHub** if you want the editor to commit directly to your fork.
4. Choose **Clipboard** if you prefer to copy and paste the keymap manually.
5. Edit layers visually.
6. Save or paste the updated result back into `config/bb9900.keymap`.
7. Wait for GitHub Actions to build a new firmware artifact.
8. Flash `bb9900-zmk.uf2`.

## When to edit the source manually

The visual editor is ideal for:

- rearranging keys,
- changing layer bindings,
- updating common behaviors,
- checking overall layout readability.

You may still want to edit the source directly for:

- experimental ZMK features,
- uncommon custom behavior definitions,
- lower-level board-specific tuning.

## Build-related reminder

This repository builds the `bb9900` target defined in `build.yaml`, so changing unrelated files is usually unnecessary for ordinary layout edits.
