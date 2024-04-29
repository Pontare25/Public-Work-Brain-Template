---
tags: []
Company: 
Created-date: <%tp.file.creation_date("YYYY-MM-DD")%>
---
%%
- Type:: #Type/Department 
%%
___
> [!Summary]- People
> ```dataview
> table
> from "03 - Resources/People"
> Where contains(Department, this.file.link) or contains(Department.Department, this.file.link)
> Where contains(file.tags, "#Type/People")
> ```

<% await tp.file.move("99 - Meta/Reference notes/Companies/Departments/"+ tp.file.title) %>