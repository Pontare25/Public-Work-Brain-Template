---
Parents:
  - "[[02 - Projects MOC]]"
Assignment: "[[Assignment A]]"
Start-date: 2024-04-29
End-date: 
Deadline: 
Areas: 
tags: []
---
%%
- Type:: #Type/Project 
- Status:: #Status/Done 
%%
# Status
`INPUT[inlineSelect(option(#Status/In-Progress, In-Progress), option(#Status/Done, Done), option(#Status/Funnel, Funnel), showcase):tags]`

# About
- Project-members::
- SUM:: 


## Goals

## Description

## Todo list
```meta-bind-button
label: Add Project event
icon: "calendar"
hidden: false
class: ""
tooltip: ""
id: ProjectEvent
style: default
actions:
  - type: templaterCreateNote
    templateFile: 99 - Meta/00 - Templates/Project templates/Project event template.md
    folderPath: 01 - Projects/Project B
    fileName: New event
    openNote: true

```
```release-timeline-week
table 
Deadline, aliases
WHERE contains(file.folder, this.file.folder)
WHERE Deadline !=""
sort ASC 
```
- [ ] 
# Meetings
> [!Summary]- Meetings
> ```dataview
> table 
> SUM as Summary, AI as "Action items", tags as Tags
> FROM "08 - Meetings"
> Where contains(Projects, this.file.link)
> sort date(file.cday) DESC
> ```

> [!Summary]- People interacted with during this Project
> ```dataview
> table without ID
> Attendees as "People interacted with"
> FROM "08 - Meetings"
> where contains(Projects, this.file.link)
> FLATTEN Attendees
> GROUP BY Attendees
> ```
# Action items
> [!Todo]+
> ```dataview
> task
> FROM "08 - Meetings" or "06 - Periodic notes" or "01 - Projects"
> Where contains(text, this.file.name) or contains(Projects, this.file.link) or contains(Parents, this.file.link)
> Where !contains(list("x"), status)
> Where text !=""
> group by file.link
> sort date(file.cday) ASC
> ```

> [!Done]-
> ```dataview
> task
> FROM "08 - Meetings" or "06 - Periodic notes" or "01 - Projects"
> Where contains(text, this.file.name) or contains(Projects, this.file.link) or contains(Parents, this.file.link)
> Where contains(list("x"), status)
> group by file.link
> ```
# Related
- REL::

> [!Summary]- Supporting notes
> ```dataview
> Table
> SUM as Summary, Status
> WHERE contains(file.folder, this.file.folder)
> WHERE file.path != this.file.path
> ```

