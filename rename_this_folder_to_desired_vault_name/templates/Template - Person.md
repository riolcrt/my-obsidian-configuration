<%* 
let personName = await tp.system.prompt("Person name")
let company = await tp.system.prompt("Company")
await tp.file.rename(`${personName}`) 
%>

---
tags: ["person"]
---

## Contact data
- Phone
- Email

## Company historical
<%`[[${company}]]`%>

## Related with