<%* 
const today = tp.date.now("YYYY-MM-DD")

const projectsRootFolder = "projects"
const projects = Array.from(new Set(app.vault.getFiles().map(x => x.path.split("/")).filter(x => x.length > 1).filter(x => x[0] == projectsRootFolder).map(x => x[1]))).filter(x => !x.includes(".md"))

const projectAcronym = await tp.system.suggester(projects, projects, true, "Project Acronym")

const taskName = await tp.system.prompt("Task Title")

const targetFolder = `${projectsRootFolder}/${projectAcronym}/tasks`

try {
	await app.vault.createFolder(targetFolder)
} catch {
	console.log("Skip")
}

await tp.file.move(`${targetFolder}/Task - ${projectAcronym} - ${taskName}`) 

%>

---
tags: ["note/task"]
---

- [ ] <%`${projectAcronym} - ${taskName}`%> 📅 <%today%>


## Description
## Resources
## Dev Journal
## Result