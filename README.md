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
[[Home]].

## Structure

```
00 - Maps of Content/   index pages — Home.md and MOC - *.md
01 - Projects/          time-bounded work with a deliverable
02 - Areas/             ongoing responsibilities, no end date
03 - Resources/         notes about a source
04 - Permanent/         distilled evergreen notes
05 - Fleeting/          scratch; where new notes land by default
06 - Notes/             Daily/ Weekly/ Meetings/ Tasks/
07 - Archives/          retired material
99 - Meta/              templates and vault plumbing
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

## Tasks

Tasks live in two places, by size.

- **Tracked tasks** are [TaskNotes](https://tasknotes.dev/) notes in
  `06 - Notes/Tasks/`, one note per task. Anything with a deadline, or work over
  more than one day, goes here. Open them with *TaskNotes: Open tasks view*; the
  views are the `.base` files in `Tasks/Views/`.
- **Small same-day items** stay as checkboxes under `## Tasks` in the daily note.

A meeting action that needs tracking is written in the meeting note as a link to
its task note, with no checkbox. Keep **one state per task**: a task tracked in
`06 - Notes/Tasks/` has its status there and nowhere else.

The TaskNotes HTTP API and MCP server are off. If you turn them on, the plugin
keeps an auth token in `.obsidian/plugins/tasknotes/data.json`, as it does for
any calendar subscription URL, so don't commit that file afterwards.

## Other note templates

Insert these with Templater; no folder applies them automatically.

- `(TEMPLATE) Literature note` for a paper, talk or other source.
- `(TEMPLATE) Topic note` for working through a subject across several sources.
- `(TEMPLATE) Unique` for everything else.

## Reviews

- **Weekly, about 15 minutes.** Walk the week's daily notes, promote what's worth
  keeping, and write the summary in the weekly note. Stop at 15 minutes; a rough
  review beats a skipped one.
- **Monthly.** Drain `05 - Fleeting/`: promote it, archive it, or leave it if
  you're still gathering. Move finished projects to `07 - Archives/`.
- **Quarterly.** Check that each Map of Content still reflects reality, and that
  every non-trivial note is reachable from one.

## First run

1. Open the folder as a vault. Obsidian will ask you to trust the bundled
   community plugins; accept, or enable them one at a time under *Settings →
   Community plugins*.
2. *Settings → Appearance* — the theme is **Encore** with several CSS snippets
   on. It expects **Fira Sans** and **JetBrainsMono Nerd Font** to be installed
   on your system and falls back to Obsidian's defaults if they aren't. Change
   any of it.
3. Search the vault for `<` to find the placeholders left for you to fill in.

One example note sits in each folder to show the frontmatter and house style,
plus a sample daily, weekly, meeting and task note so the Dataview and Tasks queries
on [[Home]] have something to display. Delete them once you have your own.

## Not included

Personal notes, the workspace layout, the recent-files list and plugin caches.
Obsidian regenerates the last three on first open.

## Credits

This vault started from
**[CyanVoxel's Obsidian Vault Template](https://github.com/CyanVoxel/Obsidian-Vault-Template)**
and owes it the folder philosophy and a good deal of its look. Seven of the CSS
snippets under `.obsidian/snippets/` are CyanVoxel's work, redistributed here
unchanged, along with the CSS-class reference notes in
`99 - Meta/Preloaded Classes/`. Newer versions of those snippets live in their
own repositories, linked from that template's README — worth pulling from the
source rather than from here.

Go look at the original. If you like what this vault does, a lot of the credit
belongs there.

## Licence

The MIT License in [`LICENSE`](LICENSE) covers the original content here: the
folder structure, templates, documentation and Obsidian settings.

It does **not** cover the bundled third-party material — CyanVoxel's snippets,
the 25 community plugins under `.obsidian/plugins/` and the themes.
Those keep their own copyright and licences, listed in [`NOTICE`](NOTICE).

If you would rather not have redistributed plugin code in your own fork, delete
`.obsidian/plugins/` and reinstall from Obsidian's community plugin browser.
