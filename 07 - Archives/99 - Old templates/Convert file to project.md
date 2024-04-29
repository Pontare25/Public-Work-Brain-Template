<%*
setTimeout(() => {
  app.fileManager.processFrontMatter(tp.config.target_file, frontmatter => {
// Update or create key "father"
  frontmatter["Type"] = "Project";
  // Update or create key "son"
  frontmatter["Assignment"] = null;
  frontmatter["Start-date"] = "";
  frontmatter["End-date"] = "";
  frontmatter["Areas"] = null;
  // Delete key "mother" (if present)
  //delete frontmatter["mother"];
  })
}, 200) // the reason for the timeout is to let the template complete first
-%>
# About
- Project-members::
## Description

## Definition of Done
- DoD::
# Meetings
> [!Summary]- Meetings
> ```dataview
> table 
> SUM as Summary, AI as "Action items", tags as Tags
> From "02 - Areas/01 - Meetings"
> Where contains(Projects, this.file.link)
> sort file.cdate DESC
> ```
# Action items
> [!Todo]+
> ```dataview
> task
> From "02 - Areas/01 - Meetings" or "06 - Periodic notes"
> Where contains(text, this.file.name) or contains(Projects, this.file.link)
> Where !contains(list("x"), status)
> group by file.link
> ```

> [!Done]-
> ```dataview
> task
> From "02 - Areas/01 - Meetings" or "06 - Periodic notes"
> Where contains(text, this.file.name) or contains(Projects, this.file.link)
> Where contains(list("x"), status)
> group by file.link
> ```

<% await tp.file.move("01 - Projects/"+tp.file.title+"/00 - "+tp.file.title)%>