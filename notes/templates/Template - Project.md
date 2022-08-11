<%* 
let projectName = await tp.system.prompt("Project Name")
let acronym = await tp.system.prompt("Acronym")
let aliases = ""

const projectsRootFolder = "projects"
const targetFolder = `${projectsRootFolder}/${acronym}`

try {
	await app.vault.createFolder(targetFolder)
} catch {
	console.log("Skip")
}

if (projectName == acronym) {
	await tp.file.move(`${targetFolder}/Project - ${acronym}`) 
	aliases = `"${acronym}"`
} else 
{
	await tp.file.move(`${targetFolder}/Project - ${acronym} - ${projectName}`) 
	aliases = `"${acronym}", "${projectName}"`
}
%>

---
aliases: [<%aliases%>]
tags: ["project"]
acronym: "<%acronym%>"

---

## Description
<%tp.system.clipboard()%>
<%tp.file.cursor(1)%>

## Resources
```expander
file:" <%acronym%> " tag:resource
```
<-->

## Apps
```expander
file:" <%acronym%> " tag:development
```
<-->

## Meeting Notes
```dataview
TASK 
FROM #note/meeting
WHERE contains(file.name, "<%acronym%>")
```

## Recent Related Tasks
```dataview
TASK 
FROM #note/task
WHERE contains(file.name, "<%acronym%>") AND file.mday > (date(now) - dur(14 days)) 
```