<%* 
const cache = await  app.metadataCache;
const tags = Object.keys(cache.getTags()).filter(x => x.includes("#tech"))

let techName = await tp.system.prompt("Tech Name")
let techType = await tp.system.suggester(tags, tags, true, "Select Tag")

const targetFolder = techType.slice(1)

try {
	await app.vault.createFolder(targetFolder)
} catch {
	console.log("Skip")
}

await tp.file.move(`${targetFolder}/${techName}`) 

%>

---
tags: ["<%techType%>"]
---

🌐 - https://tech.io

## Resources
### Videos
### Tutorials