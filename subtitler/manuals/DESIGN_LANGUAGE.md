# Subtitler design language

This is the visual reference for anyone changing the Subtitler interface. It
describes the existing visual language rather than proposing a redesign. Keep
new work recognisably within it unless the project owner explicitly asks to
change the direction.

## Character

The site is **Swiss Modernist 2.0**: a clear editorial grid, strong alignment,
visible construction lines, compact functional labels, and a small set of
bright signal colours. It should feel like a carefully typeset production tool,
not a rounded consumer dashboard.

The modern part comes from the responsive layout, dark-mode tokens, live media
surfaces, and restrained colour mixing. The Swiss part comes from hierarchy,
whitespace, square corners, thin rules, and letting layout do the organising.

## Palette

The four-colour band at the top is an important identity element. In order, it
is **violet → lilac → orange → aquamarine**. Preserve that order and use the
colours as signals rather than decorative noise.

| Token | Light value | Intended role |
| --- | --- | --- |
| `--paper` | `#F5F1FB` | Page field; the faintly tinted paper background. |
| `--surface` | `#FFFFFF` | Panels, cards, and the main workspace frame. |
| `--ink` | `#221A3E` | Primary text and decisive borders. |
| `--ink-2` | `#6A5F8C` | Secondary labels and quieter metadata. |
| `--hair` | `#D8CFEA` | Fine construction rules and control borders. |
| `--violet` | `#5B3FD4` | First band segment and a strong structural accent. |
| `--lilac` | `#CDB9F2` | Second band segment and softer selection emphasis. |
| `--lilac-soft` | `#EAE2F8` | Recessed control and timeline background. |
| `--orange` | `#FF5C1F` | Primary action, active tab, warning, focus, and playhead. |
| `--aqua` | `#35D9C0` | Selection, success, and waveform/region accent. |
| `--aqua-ink` | `#0E6B5E` | Readable dark text used with the aqua signal. |

Dark mode remaps the same semantic tokens. Add colours through these tokens;
do not hard-code a light-only colour into a new component.

## Typography and rhythm

- Use the grotesk system stack for interface text and `--mono` for timecodes,
  keyboard keys, logs, and other technical values.
- Labels use the `eyebrow` treatment: small uppercase text, generous tracking,
  and muted `--ink-2`. It establishes hierarchy without large headings.
- Buttons use compact uppercase labels with tracking. Avoid oversized, soft,
  or playful typography.
- Keep spacing deliberate and modular: the interface already uses 8, 10, 12,
  14, 16, 20, 24, 28, and 32 px steps. Prefer an existing step over an
  arbitrary new value.

## Layout and surfaces

- The main workspace is a single square-cornered frame with a tab rule across
  its top. Do not put its core contents inside unrelated cards.
- The keyboard legend is a separate appendix to the left of that frame on wide
  screens. It is a sibling, not an embedded section of a tab panel. On narrow
  screens it may move below the workspace.
- Panels use thin `--hair` borders and flat fills. Avoid rounded corners,
  drop shadows, glass effects, gradients used as decoration, or excessive
  nested cards.
- Tables, timelines, input rows, and shortcut lists should read as a precise
  grid. Borders must form complete, closed rectangles; do not leave a missing
  final/right/bottom rule because of selector ordering.
- Use whitespace to separate groups. The UI should feel calm and technical,
  not dense or ornamental.

## Interaction signals

- Orange is the action/attention colour: primary button, active-tab underline,
  playhead, keyboard focus, and error state.
- Aquamarine is the selected/success colour: selected row, clip region,
  successful connection, and secondary active controls.
- Hover and active states should be subtle changes to existing flat surfaces,
  not animated or elevated cards.
- Keep visible focus outlines for keyboard operation.

## Shortcut appendix rules

- The legend has one closed outer border and one rule between every row.
- Keep the shortcut and its explanation in a two-column row so descriptions
  begin on a consistent vertical line.
- Both columns are left-aligned. Key combinations must not be right-aligned
  merely to make their right edges line up.
- Keyboard keys use the existing square, bordered `kbd` treatment. Combined
  keys use a small inline gap and separator.

## Change-control workflow

For normal UI iterations, make and verify the requested changes **without
staging or committing them**. Present the result for the project owner to
review first. Stage and commit only after they explicitly request it, and only
to the branch they name. This preserves an easy path to revise or abandon an
approach before it becomes project history.
