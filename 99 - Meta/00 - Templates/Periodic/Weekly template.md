---
Parent-date:
  - "[[{{date:YYYY-MM-MMMM}}]]"
tags:
  - "#Type/Periodic/Weekly"
Created-date: <%tp.file.creation_date("YYYY-MM-DD")%>
SUM:
---
# Projects
## Project Deadlines
```release-timeline-week
table 
Deadline, aliases 
From "01 - Projects" or "07 - Archives/01 - Inactive Projects"
Where Deadline >= date({{date:YYYY-MM-DD}}) AND Deadline <= date(<%tp.date.now("YYYY-MM-DD", "P4M")%>)
Sort asc 
```
## Active Projects
```dataview
table
SUM AS Summary, split(
    filter(file.tags,
       (t) => startswith(t, "#Status")
    )[0],
    "/"
  )[1] as Status, Deadline
From "01 - Projects"
where contains(tags, "#Type/Project/Main-Project")
where !contains(Status, "#Status/Done")
```
# Weekly goals
- [ ] 

# Reflection
- SUM::
## Daily summaries
```dataview
Table
SUM as Summary
from "06 - Periodic notes/01 - Daily"
Where contains(Parent-date, this.file.link)
Sort file.name ASC
```
## What did I accomplish this week?
- POS::

> [!Summary]- Achievements from Daily's
>```dataview
>Table
>POS as Accomplishments
>from "06 - Periodic notes/01 - Daily"
>Where contains(Parent-date, this.file.link)
>Where POS
>Sort file.name ASC
>```
## What could I have done better this week?
- NEG::

> [!Summary]- Challenges from Daily's
>```dataview
>Table
>NEG as Challenges
>from "06 - Periodic notes/01 - Daily"
>Where contains(Parent-date, this.file.link)
>Where NEG
>Sort file.name ASC
>```
## What do I want to achieve next week?


> [!Important]+ Ideas from Daily's
>```dataview
>Table
>IDEA as Ideas
>from "06 - Periodic notes/01 - Daily"
>Where contains(Parent-date, this.file.link)
>Where IDEA
>Sort file.name ASC
>```
# Todo's
## Notes to process
```dataview
table
file.cday as "Created date", date(today)-date(file.cday) as "Time alive"
From !"99 - Meta/00 - Templates"
where contains(file.tags, "#Inbox")
```

> [!Todo]- Todo's created this week
> ```dataview
> task
> where date(file.cday) >= date({{date:YYYY-MM-DD}}) and date(file.cday) <= date({{ date+6d : YYYY-MM-DD }})
> where text !=""
> group by file.link
> sort date(file.cday)
> ```

> [!Done]- Todo's completed this week
> ```dataview
> task
> where text !=""
> where completion >= date({{date:YYYY-MM-DD}})) and completion <= date({{ date+6d : YYYY-MM-DD }})
> group by file.link
> sort date(file.cday)
> ```
## Meetings
> [!Summary]- Interactions during the week
> ```dataview
> table without ID
> Attendees as Interactions
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> Flatten Attendees
> Group by Attendees
> Sort date(Meeting-start)
> ```

> [!Summary]- [[{{date:YYYY-MM-DD}}|Monday]]
> ```dataview
> Table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> where contains(Parent-date, [["{{date:YYYY-MM-DD}}]])
> Sort date(Meeting-start) ASC
> ```

> [!Summary]- [[{{date+1d:YYYY-MM-DD}}|Tuesday]]
> ```dataview
> Table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> where contains(Parent-date, [[{{date+1d:YYYY-MM-DD}}]])
> Sort date(Meeting-start) ASC
> ```

> [!Summary]- [[{{date+2d:YYYY-MM-DD}}|Wednesday]]
> ```dataview
> Table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> where contains(Parent-date, [[{{date+2d:YYYY-MM-DD}}]])
> Sort date(Meeting-start) ASC
> ```

> [!Summary]- [[{{date+3d:YYYY-MM-DD}}|Thursday]]
> ```dataview
> Table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> where contains(Parent-date, [[{{date+3d:YYYY-MM-DD}}]])
> Sort date(Meeting-start) ASC
> ```

> [!Summary]- [[{{date+4d:YYYY-MM-DD}}|Friday]]
> ```dataview
> Table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> where contains(Parent-date, [[{{date+4d:YYYY-MM-DD}}]])
> Sort date(Meeting-start) ASC
> ```

> [!Summary]- [[{{date+5d:YYYY-MM-DD}}|Saturday]]
> ```dataview
> Table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> where contains(Parent-date, [[{{date+5d:YYYY-MM-DD}}]])
> Sort date(Meeting-start) ASC
> ```

> [!Summary]- [[{{date+6d:YYYY-MM-DD}}|Sunday]]
> ```dataview
> Table
> SUM as Summary, AI as "Action items"
> From "08 - Meetings/{{date:YYYY}}/{{date:[W]WW}}"
> where contains(Parent-date, [[{{date+6d:YYYY-MM-DD}}]])
> Sort date(Meeting-start) ASC
> ```
