# ghostnote

A minimalist, command-driven notes tool with **text and drawing** — runs
entirely in your browser, no account, no cloud, no install. Type notes, sketch
on a canvas layer, and drive everything through a `:` command bar inspired by
modal editors.

Ghostnote is the web client of a small local-first ecosystem: the same notes are
shared with a terminal editor (**ghostnote-tui**) and a CLI + sync daemon
(**ghostnote-cli**) through a common `ghostnote/v1` format.

**Live:** https://drgropp.github.io/ghostnote/

## Features

- **Text + draw layers** — write notes and sketch freehand on the same page.
- **Command-driven** — press `:` for everything; no chrome, no clutter.
- **Local-first** — notes live in your browser (localStorage); nothing is sent
  anywhere by default.
- **Theming** — recolor the UI, including animated rainbow modes.
- **Portable notes** — export/import the `ghostnote/v1` JSON format, shared
  across the whole ecosystem.
- **Optional sync** — push/pull to a local `ghostnote-cli` daemon to share notes
  with the terminal tools on your machine.

## Using it

Just start typing. Press `:` to open the command bar, type a command, hit Enter.
`Esc` closes the bar. Press `:help` for the full list in-app.

### Core commands

| Command | Description |
|---|---|
| `:type` / `:draw` / `:erase` | Switch between text, drawing, and eraser modes |
| `:text [color]` | Set the text color (also `:text rgb` for rainbow) |
| `:ink [color]` | Set the pen color |
| `:weight [n]` / `:eraser [n]` | Pen thickness / eraser size |
| `:size [px]` | Text size |
| `:ghost [0-100]` | Background opacity |

### Notes

| Command | Description |
|---|---|
| `:save [name]` | Save the current note |
| `:open [name]` | Load a saved note |
| `:notes` | Browse saved notes |
| `:delete [name]` | Delete a note |
| `:new` | Start a fresh note |
| `:export [name]` | Download a note as `.ghostnote.json` |
| `:import` | Load a `.ghostnote.json` from disk |
| `:png` | Export the note as a PNG image |

### Appearance

| Command | Description |
|---|---|
| `:ui [color]` | Set accent + cursor color |
| `:ui accent/cursor [color]` | Set one slot |
| `:ui rgb` / `:ui rgb spectrum` / `:ui rgb static` | Rainbow themes |
| `:reset` | Restore the default theme |

### Sync (optional)

| Command | Description |
|---|---|
| `:push [name]` | Send a note to a running `ghostnote-cli` daemon |
| `:pull [name]` | Fetch a note from the daemon |
| `:sync` | List notes on the daemon |
| `:daemon [url]` | Set the daemon address (default `http://127.0.0.1:7777`) |

To use sync, run `ghostnote daemon` from
[ghostnote-cli](https://github.com/drgropp/ghostnote-cli) on the same machine.

## The Ghostnote ecosystem

- **ghostnote** — this web app (text + draw, in the browser)
- **ghostnote-tui** — a terminal note editor
- **ghostnote-cli** — a CLI and local sync daemon

All three share the `ghostnote/v1` note format. A note made in one shows up in
the others (via export/import or the local daemon).

## Running locally

It's a single `index.html` — open it in a browser, or serve the folder:

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## License

MIT
