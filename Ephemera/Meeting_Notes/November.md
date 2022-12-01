---
title: Meeting Notes, November 2022
author: Tucker Bradford
banner: "![[BA4EC011-DC38-4841-9ABB-5D30496F66BA_1_105_c.jpeg]]"
---

```dataview
LIST WHERE contains(file.folder, this.file.folder) 
SORT file.name DESC
```
---
```dataviewjs
const currentPath = `${dv.current().file.path.split('/').slice(0,-1).join('/')}`
let pages = dv.pages(`"${currentPath}"`)

pages.values = pages.values.map(v => {
	v.fileDate = v.file.name.split('-').slice(0,3).join('-')
	return v
})

for await (let page of pages.groupBy(p => p.fileDate) ){
	dv.header(2, moment(page.key).format('dddd MMMM Do YYYY'))
	page.rows.map(p => {
		const title = p.title ? p.title : p.file?.name
		dv.el('p', `- [[${p.file?.name}]]`)
		if (p.tags) console.log(p.tags)
	})	
}


```
