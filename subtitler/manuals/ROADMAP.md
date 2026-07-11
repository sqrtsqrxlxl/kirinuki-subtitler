# Roadmap

Plain-language milestone map. This is for ME to read, not an AI agent — no technical
detail here, just "what's the theme of each version." When a milestone is done, its
items move into CHANGELOG.md and get crossed off here.

---

**Naming convention:** `0.x` = not usable yet, do not download. `1.0+` = usable.
Once the current beta scaffolding is solid, it ships as **v1.0**, not v0.2.x.

---

## v1.0 — Usable beta (current)

The smallest usable version: a single user can come in and make Japanese → Chinese
subtitles/clips, start to finish, without it breaking. Everything up through the
Editor panel polish belongs here. Once this is solid, this milestone is done and it
ships as v1.0 — the first version worth telling someone to download.

---

## v2.0 — Translate from Japanese into more target languages

Right now it's hardcoded ja → zh. Open this up so the app can ship to international
audiences, not just Chinese speakers.

- [ ] Japanese → English
- [ ] Japanese → Indonesian
- [ ] Japanese → Thai
- [ ] Japanese → Spanish
- [ ] Japanese → French
- [ ] Japanese → German
- [ ] (Whatever else comes up — the point is the pipeline supports "pick any target
      language," not that every language is added on day one.)

---

## v3.0 — Multi-speaker support

Important — this is coming up because I'm actively testing with a multi-speaker
source video right now.

- [x] Distinguish between different speakers in a clip. (shipped early in v0.2.6)
- [x] Support overlapping subtitles — two lines on screen at the same time when two
      people talk over each other. (shipped early in v0.2.6)
- [x] Each speaker gets their own consistent style (font/color) and consistent screen
      position, so the viewer can tell speakers apart at a glance without rereading.
      (shipped early in v0.2.6)

---

## v4.0 — Internationalization (i18n) of the UI

Chinese users (and others) shouldn't have to read English to use this app.

- [ ] Translate the app's own interface (buttons, labels, menus, tooltips) — not the
      subtitles it produces, the app's UI itself.
- [ ] Keep translations in a separate, clearly organized document/folder — not buried
      in code — so that later, other people can contribute translations for their own
      language without needing to touch anything else.
- [ ] Pick the first non-English UI language (Chinese, presumably) and get it fully
      covered as the proof this system works.

---

## Not yet scheduled

Ideas that exist but don't have a milestone slot yet. Once a theme has enough of
these clustered together, it graduates into its own version above.

- User documentation — a plain-language manual, ideally built into the app itself
  (not a separate doc people have to go find), so people don't have to click around
  and guess.

---

## Long-term / distant roadmap

Real goals, but far out — no version number yet, just parked here so they don't get
lost.

- **Custom themes** — let the user pick their own color palette for the app itself
  (start simple: just a color palette, not a full re-skin).
- **Translate from source languages other than Japanese** — e.g. English → Spanish,
  English → French, and other source/target combinations, so this eventually serves
  "everyone," not just people translating out of Japanese.

---

## How to use this file

- A milestone is a **theme**, not a deadline. "Would the app be meaningfully better
  at one thing if I only finished this?" — that's the bar.
- When a milestone's items are all done, write the version entry in `CHANGELOG.md`,
  tag the commit (`git tag vX.Y.Z`), and delete or check off the section here.
- Small one-off ideas that don't belong to a milestone yet go in `BACKLOG.md`
  instead, until they cluster into a theme worth its own version above.
