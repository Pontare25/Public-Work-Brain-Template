---
tags:
  - Type/MOC
aliases:
  - Projects MOC
---
up:: [[01 - Assignments MOC|Assignments MOC]]
___
# Active
> [!Todo]+ Active
> ```dataview
> table 
> rows.file.link as Projects
> from "01 - Projects"
> where contains(file.tags, "#Type/Project") AND (!contains(file.tags, "#Status/Done") OR !contains(file.tags, "#Status/Funnel"))
> Group by Assignment
> Sort file.name 
> ```
# Archived
> [!Done]+ Archived
> ```dataview
> table 
> rows.file.link as Projects
> from "07 - Archives"
> where contains(file.tags, "#Type/Project")
> Group by Assignment
> Sort file.name 
> ```
