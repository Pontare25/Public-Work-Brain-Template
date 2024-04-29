---
tags: 
aliases: []
Created-date: <%tp.file.creation_date("YYYY-MM-DD")%>
Projects: 
SUM: 
Company: 
Department: 
Cover: 
LinkedIn: 
Relation: 
Met-through: 
Skills:
---
%%
- Type:: #Type/Person 
%%
___
# About
`="![ProfileCover|250](" + this.Cover + ")"`
<% await tp.file.move("99 - Meta/Reference notes/People/"+ tp.file.title) %>
```meta-bind
INPUT[textArea(title(Summary), 
class(meta-bind-full-width), class(meta-bind-high)):SUM]
```
# Meetings
> [!Summary]- Last 10 meetings
> ```dataview
> table
> SUM as Summary, AI as "Action items", Projects
> FROM "08 - Meetings"
> Where contains(Attendees, this.file.link)
> sort date(file.cdate) DESC
> limit 10
> ```

> [!Summary]- All meetings
> ```dataview
> table
> SUM as Summary, AI as "Action items", Projects
> FROM "08 - Meetings"
> Where contains(Attendees, this.file.link)
> sort date(file.cdate) DESC
> ```
# Action items
> [!Todo]+ Shared todos
> ```dataview
> task
> Where contains(text, this.file.name)
> Where !contains(list("x"), status)
> group by file.link
> ```
 
> [!Todo]- Action items from meetings
> ```dataview
> Table
> AI as "Action items"
> FROM "08 - Meetings"
> where contains(AI, this.file.name)
> group by file.link
> ```

> [!Done]-
> ```dataview
> task
> Where contains(text, this.file.name)
> Where contains(list("x"), status)
> Group by file.link
> ```
# Projects
> [!Todo]- Active projects
> ```dataview
> table
> SUM as Summary
> from "01 - Projects"
> where contains(Project-members, this.file.link)
> where contains(file.tags, "#Type/Project")
> where !contains(file.tags, "#Status/Done")
> ```

> [!Done]- Completed projects
> ```dataview
> table
> SUM as Summary
> from "01 - Projects" or "07 - Archives"
> where contains(Project-members, this.file.link)
> where contains(file.tags, "#Type/Project")
> ```
# Logs
> [!Quote]- Logs
> ```dataview
> table
> LOG as Quotes
> FROM "08 - Meetings"
> WHERE contains(LOG, this.file.name)
> sort date(file.cday) DESC
> ```

