<%*
  let qcFileName = await tp.system.prompt("Note Title")
  titleName = tp.date.now("YYYY-MM-DD") + "-" + qcFileName
  await tp.file.rename(titleName)
  await
  tp.file.move("/Ephemera/Meeting_Notes/" + tp.date.now('YYYY') +
  "/" + tp.date.now('MMMM') + "/"+ titleName)
-%>
---
title: <% qcFileName %>
date: <% tp.file.creation_date("YYYY-MM-DD HH:mm:ss") %>
tags: meeting_note
topic: 
---
# <% tp.date.now('dddd, MMMM Do YYYY') + " - [[" + qcFileName + "]]"%>
**Attendees:** 
<%* tp.file.cursor() -%>

---
## Goals / agenda:
1. 

## Discussion notes:
- 

## Action items:
- 
