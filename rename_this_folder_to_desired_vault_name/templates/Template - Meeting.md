
<%* 
let today = tp.date.now("YYYY-MM-DD")
let meetingTitle = await tp.system.prompt("Meeting Title")
await tp.file.rename(`${today} ${meetingTitle}`) 
%>

---
duration: ""
tags: ["note/meeting"]
---

# [[<% today  %>]] <% meetingTitle %>

#### Summary
<% tp.file.cursor(1) %>

#### Tasks