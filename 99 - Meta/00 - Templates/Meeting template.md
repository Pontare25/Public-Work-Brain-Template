---
Parent-date:
  - '[[<%tp.date.now("YYYY-MM-DD")%>]]'
Created-date: <%tp.file.creation_date("YYYY-MM-DD")%>
Meeting-start: <%tp.date.now("YYYY-MM-DD HH:mm")%>
Meeting-end:
Projects: 
Meeting-series: 
Related-topics: 
Related-areas: 
Location:
---
# <%tp.date.now("YYYY-MM-DD dddd")%>
%%
- Type:: <%tp.system.suggester(["Personal", "Workshop", "Informational", "Support", "Internal"], ["#Type/Meeting/Personal", "#Type/Meeting/Work/Workshop", "#Type/Meeting/Work/Informational", "#Type/Meeting/Work/Support", "#Type/Meeting/Work/Internal"])%>
%%
# Info
- Organizer::
- Attendees::
## Summary
 ```dataview
table without ID
SUM as Summaries
WHERE file.path = this.file.path
WHERE text!=""
```
## Action items
```dataview
table without ID
AI as "Action items"
 WHERE file.path = this.file.path
WHERE text !=""
```
### My todo's
- [ ] 
## Links
> [!Summary]- URL Links
> ```dataview
> table without ID
> URL as Link
> WHERE file.path = this.file.path
> WHERE text!=""
> ```
___

%%
___
PDF Page break
___
%%
<div style="page-break-after: always;"></div>


# Agenda
<% await tp.file.move("08 - Meetings/"+tp.date.now("YYYY")+"/"+tp.date.now("[W]WW")+"/" +tp.date.now("YY[w]WW[d]d")+ "- ")%>
# Meeting notes
%%
## Topic
- Presenters:: 
- SUM::
- AI::
- URL::
%%
