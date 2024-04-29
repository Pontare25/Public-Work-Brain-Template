---
tags: []
Created-date: 2024-04-27
---
%%
- Type:: #Type/Company 
%%
___
> [!Summary]- Departments
> ```dataview
> table
> From "99 - Meta/Reference notes/Companies/Departments"
> Where contains(Company, this.file.link)
> Where contains(tags, "#Type/Department")
> ```

> [!Summary]- People
> ```dataview
> table
> Department
> from "99 - Meta/Reference notes/People"
> Where contains(Company, this.file.link) or contains(Department.Company, this.file.link)
> Where contains(tags, "#Type/Person")
> ```
