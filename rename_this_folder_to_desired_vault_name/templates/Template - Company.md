<%* 
let companyName = await tp.system.prompt("Company Name")
await tp.file.rename(`${companyName}`) 
%>

---
tags: ["company"]
---


🌐 - https://company.io


### Employees
```expander
<%companyName%> tag:person
```
