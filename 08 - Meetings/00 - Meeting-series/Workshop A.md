---
Projects: 
Areas: 
Organizer:
---
%%
- Type:: #Type/Meeting/Work/Meeting-series 
%%
___
# About
- SUM::
## General Agenda

# Meetings
> [!Summary]- Last 10 Meetings
> ```dataview
> table
> SU as Summary, AI as "Action items"
> From "08 - Meetings"
> where contains(Meeting-series, this.file.link)
> Sort date(Created-date) DESC
> limit 10
> ```

> [!Summary]- All Meetings
> ```dataview
> table
> SU as Summary, AI as "Action items"
> From "08 - Meetings"
> where contains(Meeting-series, this.file.link)
> Sort date(Created-date) DESC
> ```

> [!Summary]- People interacted with during this meeting series
> ```dataview
> table without ID
> Attendees as "People interacted with"
> FROM "08 - Meetings"
> where contains(Meeting-series, this.file.link)
> FLATTEN Attendees
> GROUP BY Attendees
> ```
# Action items
> [!Todo]
> ```dataview
> task
> FROM "08 - Meetings"
> where contains(Meeting-series, this.file.link)
> where contains(list(" "), status)
> where text !=""
> group by file.link
> sort date(file.cday) ASC
> ```

> [!Done]- Done or won't do
> ```dataview
> task
> FROM "08 - Meetings"
> where contains(Meeting-series, this.file.link)
> where contains(list("x", "-"), status)
> group by file.link
> sort date(file.cday) ASC
> ```

