---
date: <% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYYMMDD") %>T<% tp.date.now("HH:mm") %>
tags:
  - Daily
cssclasses:
  - daily
  - <% tp.date.now("dddd", 0, tp.file.title, "YYYYMMDD").toLowerCase() %>
status: in-progress
type: daily
---
# DAILY NOTE
## <% tp.date.now("dddd, MMMM Do, YYYY", 0, tp.file.title, "YYYYMMDD") %>

← [[<% tp.date.now("YYYYMMDD", -1, tp.file.title, "YYYYMMDD") %>]] | [[<% tp.date.now("YYYYMMDD", 1, tp.file.title, "YYYYMMDD") %>]] →
***
## Journal
#### Notes

...
***
## Tasks
- [ ] 


---
## Meetings

