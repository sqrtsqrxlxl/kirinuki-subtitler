# Working on Subtitler

This file describes how this project is actually run, iteration to iteration.
Read it before doing project-planning work here (triaging feedback, writing an
iteration manual, updating CHANGELOG/ROADMAP/BACKLOG).

## The three planning documents

- **BACKLOG.md** — raw, unsorted. Bugs and small ideas land here the instant
  they're found, no filtering.
- **ROADMAP.md** — sorted into milestones (themed future versions), plus a
  long-term/distant section for things with no version number yet.
- **CHANGELOG.md** — shipped history, one entry per version, tagged by panel
  (01 Clips / 02 Editor / 03 Export / Home / Settings / Debug / Backend), split
  into Bug fixes vs New features.

Flow: **raw feedback → BACKLOG or ROADMAP → iteration manual → code → CHANGELOG.**

## The iteration loop

1. **User tests the app** and dumps unfiltered feedback into the chat — bug
   reports and feature wants mixed together, in whatever order they come to
   mind, voice-dictated (expect transcription artifacts, e.g. "Foster
   Whisperer" = faster-whisper, "shares" = cursor).
2. **Claude's job at this step is sorting only** — no coding yet. Take the raw
   dump and file each item into `BACKLOG.md` (bugs / small ideas) or
   `ROADMAP.md` (if it's part of an existing or new milestone theme). Don't
   invent scope beyond what was said.
3. **Fable decides what this iteration covers.** A strong model (Fable) reads
   the current backlog/roadmap state and picks what goes into *this* version —
   then writes a numbered work-order manual (`ITERATION_N.md` pattern, each
   item with Problem/Fix/VERIFY sections) aimed at a Sonnet-level implementer.
4. **Sonnet implements.** Spawn a Sonnet subagent (general-purpose, model
   sonnet) to execute the manual and test its own work.
5. **Repeat within the version** until it feels solid, then close it out:
   update `CHANGELOG.md`, tag the commit (`git tag vX.Y.Z`), check items off
   `ROADMAP.md`/delete them from `BACKLOG.md`.

This loop is why versions can move fast — the human's job is testing +
unfiltered reporting, not writing code or managing the plan by hand.

## Version numbering

- `0.x` = not usable yet, don't tell anyone to download it.
- `1.0+` = usable — first real milestone is ja→zh working end to end.
- Milestone order after that: v2.0 more target languages, v3.0 multi-speaker,
  v4.0 UI internationalization. See ROADMAP.md for current detail.

## Fixed project rules

- Never commit `subtitler/settings.json` (holds the user's DeepSeek API key)
  or `subtitler/projects/`.
- Never pipe Chinese/Japanese through the Windows terminal — write UTF-8
  Python scripts for test seeding instead.
- Design language is locked: Swiss Modernism 2.0, violet/lilac structure +
  orange actions + aqua highlights, no blue. (Full spec:
  `subtitler/manuals/DESIGN_LANGUAGE.md`.)
