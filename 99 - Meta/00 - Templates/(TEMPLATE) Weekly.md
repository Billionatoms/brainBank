---
date: <% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "gggg-[W]ww") %>T<% tp.date.now("HH:mm") %>
tags:
  - Weekly
cssclasses:
  - daily
  - weekly
status: in-progress
type: weekly
---
# WEEKLY NOTE
## <% tp.file.title %> · <% tp.date.now("D MMMM", 0, tp.file.title, "gggg-[W]ww") %> – <% tp.date.now("D MMMM YYYY", 4, tp.file.title, "gggg-[W]ww") %>

← [[<% tp.date.now("gggg-[W]ww", -7, tp.file.title, "gggg-[W]ww") %>]] | [[<% tp.date.now("gggg-[W]ww", 7, tp.file.title, "gggg-[W]ww") %>]] →
***
## Plan for this week
- **This week (<% tp.date.now("D", 0, tp.file.title, "gggg-[W]ww") %>–<% tp.date.now("D MMM", 4, tp.file.title, "gggg-[W]ww") %>), priority order.** 
1. (P1) 
2. (P2) 
3. (P3) 
4. 

See [[Home]].

---

## Daily notes

```base
formulas:
  day: 'date(file.name.slice(0, 4) + "-" + file.name.slice(4, 6) + "-" + file.name.slice(6, 8))'
  weekday: 'formula.day.format("dddd")'
properties:
  file.name:
    displayName: Note
  formula.weekday:
    displayName: Day
filters:
  and:
    - file.inFolder("06 - Notes/Daily")
    - '/^\d{8}/.matches(file.name)'
    - 'formula.day >= date("<% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "gggg-[W]ww") %>")'
    - 'formula.day <= date("<% tp.date.now("YYYY-MM-DD", 4, tp.file.title, "gggg-[W]ww") %>")'
views:
  - type: table
    name: Daily notes
    order:
      - file.name
      - formula.weekday
    sort:
      - property: file.name
        direction: ASC
```

***
## Open tasks

```dataview
TASK
FROM "06 - Notes/Daily"
WHERE !completed
  AND file.name >= "<% tp.date.now("YYYYMMDD", 0, tp.file.title, "gggg-[W]ww") %>"
  AND file.name <= "<% tp.date.now("YYYYMMDD", 4, tp.file.title, "gggg-[W]ww") %>"
GROUP BY file.link
```

***
## Progress

### <Track 1>

- 

### <Track 2>

- 

***
## Review

#### What moved

- 

#### What stalled

- 

#### Notes to write up

- 

***
## Next week

1. (P1) 
2. (P2) 
3. (P3) 
4. 
