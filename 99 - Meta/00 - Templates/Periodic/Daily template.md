---
Parent-date:
  - "[[{{date:YY[w]WW}}]]"
aliases:
  - "{{date:YY[w]WW[d]d}}"
tags:
  - "#Type/Periodic/Daily"
Created-date: <%tp.file.creation_date("YYYY-MM-DD")%>
---
[[{{date:YY[w]WW}}|Weekly note - {{date:YY[w]WW}}]]
 [[{{date-1d:YYYY-MM-DD}}|<<Yesterday]] | [[{{date+1d:YYYY-MM-DD}}|Tomorrow>>]]
--- 
# {{date:YY[w]WW - dddd}}
```meta-bind-button
label: "+ Create new meeting"
hidden: false
class: ""
tooltip: ""
id: new meeting button
style: default
actions:
  - type: templaterCreateNote
    templateFile: 99 - Meta/00 - Templates/Meeting template.md
    folderPath: 08 - Meetings
    fileName: Meeting
    openNote: true
```

```meta-bind-button
label: Add new inbox item
icon: "inbox"
hidden: false
class: ""
tooltip: ""
id: inboxBtn
style: default
actions:
  - type: templaterCreateNote
    templateFile: 99 - Meta/00 - Templates/Inbox note template.md
    folderPath: 05 - Inbox
    fileName: {{date:YYYY-MM-DD}} Inbox
    openNote: true

```
## Daily quote

<% tp.web.daily_quote() %>

# Weekly goals
```dataview
task
From "06 - Periodic notes/02 - Weekly"
Where file.name = "{{date:YY[w]WW}}"
Where text !=""
```
# Today's top 3 priorities
- [ ] 
## Brain dump
- 
- IDEA::
# Summary
- SUM::
- POS::
- NEG::
# Meetings
> [!Summary]+ Meetings
> ```dataview
> table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> Where contains(Parent-date, this.file.link)
> sort date(Meeting-start) ASC
> ```
## Todo items from today's meetings
> [!Todo]+ Todo items from today's meetings
> ```dataview
> task
> from "08 - Meetings"
> Where contains(Parent-date, this.file.link)
> where text!=""
> group by file.link
> Sort file.cday ASC
> ```

