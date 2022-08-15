<%\*
let resourceName = await tp.system.prompt("Resource Title")

const projectsRootFolder = "projects"
const projects = Array.from(new Set(app.vault.getFiles().map(x => x.path.split("/")).filter(x => x.length > 1).filter(x => x[0] == projectsRootFolder).map(x => x[1]))).filter(x => !x.includes(".md"))

const projectAcronym = await tp.system.suggester(projects, projects, true, "Project Acronym")

const cache = await app.metadataCache;
const tags = Object.keys(cache.getTags()).filter(x => x.includes("#resource")).map(x => x.split("/")[1])

let resourceType = await tp.system.suggester(tags, tags, true, "Select Tag")

const targetFolder = `${projectsRootFolder}/${projectAcronym}/resources`

try {
await app.vault.createFolder(targetFolder)
} catch {
console.log("Skip")
}

await tp.file.move(`${targetFolder}/${resourceType.charAt(0).toUpperCase()+resourceType.slice(1)} - ${projectAcronym} - ${resourceName}`)
%>

---

## tags: ["resource<%`/${resourceType.toLowerCase()}`%>"]
