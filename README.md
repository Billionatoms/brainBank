---
tags:
  - meta
date: 2026-09-08
---
# Obsidian starter vault

An empty, working Obsidian vault: a PARA-style folder skeleton, a full set of
community plugins, themes, snippets, fonts and hotkeys, and the Templater
templates that drive daily, weekly and meeting notes.

Open the folder with **Obsidian → Open folder as vault**, then start at
[[Home]]. The full conventions live in [[CLAUDE]].

## Structure

```
00 - Maps of Content/   index pages — Home.md and MOC - *.md
01 - Projects/          time-bounded work with a deliverable
02 - Areas/             ongoing responsibilities, no end date
03 - Resources/         notes about a source
04 - Permanent/         distilled evergreen notes
05 - Fleeting/          scratch; where new notes land by default
06 - Notes/             Daily/ Weekly/ Meetings/
07 - Archives/          retired material
99 - Meta/              templates, instructions, the Claude skill
```

Notes are filed by **what they are for**, not by topic. Topic lives in tags,
links and Maps of Content, so a note only gets filed once. Subfolder as deep as
you like inside any of these — nothing depends on the second level, so carve it
up however suits your work.

## The daily loop

1. Open [[Home]]. It shows the last few daily notes, the latest weekly note, and
   open tasks pulled from daily and meeting notes.
2. Capture the day in today's daily note. Bigger or still unclear? Start
   something in `05 - Fleeting/`.
3. Meetings get their own note; the daily note just points at it.
4. Once a week, open the weekly note. Promote what turned out to be worth
   keeping into `04 - Permanent/`, and index it from a Map of Content.

## Periodic notes

| | Where | Named | Made by |
|---|---|---|---|
| Daily | `06 - Notes/Daily/<MMM - YY>/` | `20260908.md` | Daily Notes + Templater folder template |
| Weekly | `06 - Notes/Weekly/` | `2026-W37.md` | Calendar plugin |
| Meeting | `06 - Notes/Meetings/` | `M20260908.md` | `(CREATE) Meeting` Templater hotkey |

Three things that look cosmetic but are not:

- The **month subfolder is part of the daily-note format** (`MMM - YY/YYYYMMDD`),
  so it rolls forward by itself. Don't create it by hand.
- The **`M` prefix on meeting notes is load-bearing.** Without it the basename
  collides with that date's daily note and `[[20260908]]` goes ambiguous.
- All three templates are applied by **Templater folder templates**, not by the
  Calendar / Daily Notes "template" setting. Leave those fields empty, or the
  template gets inserted twice, unprocessed.

The weekly template derives its Mon–Fri range from the filename, so it needs the
week to start on Monday (*Calendar → Start week on*).

## First run

1. Open the folder as a vault. Obsidian will ask you to trust the bundled
   community plugins; accept, or enable them one at a time under *Settings →
   Community plugins*.
2. *Settings → Appearance* — the theme is **Encore** with several CSS snippets
   on. Fonts load from `.obsidian/fonts/` via Custom Font Loader. Change any of
   it.
3. Search the vault for `<` to find the placeholders left for you to fill in.

One example note sits in each folder to show the frontmatter and house style,
plus a sample daily, weekly and meeting note so the Dataview and Tasks queries
on [[Home]] have something to display. Delete them once you have your own.

Empty folders carry a `.gitkeep` so the structure survives git and zip.

## Not included

Personal notes, the workspace layout, the recent-files list and plugin caches.
Obsidian regenerates the last three on first open.
