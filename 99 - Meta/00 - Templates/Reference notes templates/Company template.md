---
tags: []
Created-date: <%tp.file.creation_date("YYYY-MM-DD")%>
---
%%
- Type:: #Type/Company 
%%
___
<% await tp.file.move("99 - Meta/Reference notes/Companies/"+ tp.file.title) %>
> [!Summary]- Departments
> ```dataview
> table
> From "03 - Resources/Companies/Departments"
> Where contains(Company, this.file.link)
> Where contains(file.tags, "#Type/Department")
> ```

> [!Summary]- People
> ```dataview
> table
> Department
> from "99 - Meta/Reference notes/People"
> Where contains(Company, this.file.link) or contains(Department.Company, this.file.link)
> Where contains(file.tags, "#Type/Person")
> ```

> [!Summary]- Projects
> ```dataview
> table 
> rows.file.link as Projects, rows.Status as Status
> from "01 - Projects" OR "07 - Archives"
> where contains(file.tags, "#Type/Project")
> Group by Assignment
> Sort file.name 
> ```

