---
aliases:
  - Pontus Nellgård
Created-date: 2024-04-27
Projects: 
SUM: Pontus is a Business Analyst consultant working for Ekan management. He is a Civil-engineer and has a great interest in technology and IT.
Company:
  - "[[Ekan management]]"
Department: 
Cover: https://media.licdn.com/dms/image/C4E03AQEz92tnXS5FfA/profile-displayphoto-shrink_400_400/0/1636700036857?e=1719446400&v=beta&t=Q5wjcC4XCP-Dvwe6Ds7G-iRy-GaAYniocXCSw_FiPFM
LinkedIn: https://www.linkedin.com/in/pontus-nellgard/
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

- [ ] 

> [!Todo]- Active
> ```dataview
> table
> SUM as Summary
> from "01 - Projects"
> where contains(Project-members, this.file.link)
> where contains(tags, "Type/Project")
> where !contains(tags, "Status/Done")
> ```

> [!Done]- Archived
> ```dataview
> table
> Summary, Areas
> from "07 - Archives/01 - Projects"
> where contains(Project-members, this.file.link)
> where contains(tags, "Type/Project")
> where contains(tags, "Status/Done")
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

