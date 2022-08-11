<%* 
let resourceName = await tp.system.prompt("Development Name")

const projectsRootFolder = "projects"
const projects = Array.from(new Set(app.vault.getFiles().map(x => x.path.split("/")).filter(x => x.length > 1).filter(x => x[0] == projectsRootFolder).map(x => x[1]))).filter(x => !x.includes(".md"))

const projectAcronym = await tp.system.suggester(projects, projects, true, "Project Acronym")

const tags = Object.keys(await app.metadataCache.getTags()).filter(x => x.includes("#development")).map(x => x.split("/").slice(1)).filter(x => x.length > 0).map(x => x.join("/"))

let resourceType = await tp.system.suggester(tags, tags, true, "Select Tag")

const targetFolder = `${projectsRootFolder}/${projectAcronym}/development`

try {
	await app.vault.createFolder(targetFolder)
} catch {
	console.log("Skip")
}

await tp.file.move(`${targetFolder}/${resourceType.charAt(0).toUpperCase()+resourceType.slice(1)} - ${projectAcronym} - ${resourceName}`) 
%>

---
tags: ["development<%`/${resourceType.toLowerCase()}`%>"]
---

<%tp.file.cursor(1)%>
