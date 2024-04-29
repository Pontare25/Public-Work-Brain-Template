---
Parents:
  - '[[<%tp.date.now("YYYY-MM-DD")%>]]'
tags:
  - "#Inbox"
Created-date: <%tp.file.creation_date("YYYY-MM-DD")%>
---
<% await tp.file.move("05 - Inbox/"+tp.file.title)%>