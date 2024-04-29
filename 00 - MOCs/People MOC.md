---
tags:
  - "#Type/MOC"
---
up:: [[00 - Home|Home]]
___
# Search (within the quotation marks)
- Search:: ""
```dataview
TABLE ("![coverimg|100](" + Cover + ")") as Cover, SUM as Summary, Skills
From "99 - Meta/Reference notes/People"
where contains(lower(file.name), lower(this.search))
where contains(file.tags, "#Type/Person")
```

