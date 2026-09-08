---
aliases:
  - Vault Home
tags:
  - meta
  - home
date: 2026-09-08
type: MOC
status: reference-only
cssclasses:
  - center-titles
---
# 🏠 Home

The landing page. The queries below are live, so this page fills itself in as
you write. Everything here works out of the box; edit it freely.

## Now

```dataview
TABLE WITHOUT ID
  file.link AS "Daily",
  dateformat(date(file.name, "yyyyMMdd"), "cccc d LLL") AS "Day"
FROM "06 - Notes/Daily"
SORT file.name DESC
LIMIT 3
```

```dataview
LIST WITHOUT ID
  "Latest weekly note: " + file.link
FROM "06 - Notes/Weekly"
SORT file.name DESC
LIMIT 1
```

---

## Needs attention

### 📅 Recent open daily tasks

```tasks
not done
path includes 06 - Notes/Daily
description regex does not match /^[\s0-9:\-–—]*$/
sort by filename reverse
group by filename reverse
limit 5
```

### 🤝 Recent meeting actions

```tasks
not done
path includes 06 - Notes/Meetings
description regex does not match /^[\s0-9:\-–—]*$/
sort by filename reverse
group by filename reverse
limit 5
```

---

## Active work

Add a section per thing you are working on. The pattern: a link to its Map of
Content, then a Dataview query pulling the most recent note.

### <Your topic>

[[MOC - Example Topic]]

```dataview
LIST WITHOUT ID
  "Recent project note: " + file.link
FROM "01 - Projects"
SORT file.mtime DESC
LIMIT 1
```

---

## Navigate

- [[MOC - Example Topic]] · one line on what the map covers

Add one line per MOC as you create them.

---

Vault guide: [[README]] · Full conventions: [[CLAUDE]]
