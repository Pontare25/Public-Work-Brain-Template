---
Company: 
Start-date: 
End-date:
---
%%
- Type:: #Type/Assignment 
%%
___
# About
- Status:: <%tp.system.suggester(["In-Progress", "Done"], ["#Status/In-Progress", "#Status/Done"])%>

<% await tp.file.move("02 - Areas/02 - Work/01 - Assignments/"+tp.file.title+"/"+tp.file.title)%>

## Related Projects
```dataview
table
SUM as Summary, Status, Areas
From "01 - Projects" OR "07 - Archives/01 - Inactive Projects"
Where contains(Assignment, this.file.link)
Sort date(Start-date) ASC
```

# Related skills
- 

# Drivers
- 