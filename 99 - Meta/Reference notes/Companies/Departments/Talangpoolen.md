---
tags:
  - "#Type/Department"
Company:
  - "[[Ekan management]]"
Created-date: 2024-04-29
---

> [!Summary]- People
> ```dataview
> table
> from "03 - Resources/People"
> Where contains(Department, this.file.link) or contains(Department.Department, this.file.link)
> Where contains(Type, "People")
> ```

