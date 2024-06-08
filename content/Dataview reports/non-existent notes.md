A report to show notes which are not created but are used as a link in a note. This is could to highlight potential connections between notes. I create brackets around something that indicates to me a note needs to be created or it could indicate to me something I've highlighted as something I want in my notes. 
```dataview 
TABLE file.outlinks, file.outlinks.file.folder, file.inlinks, file.inlinks.file.folder 
FROM "Inbox" 
WHERE endswith(file.outlinks.file.folder, "folder A") OR endswith(file.inlinks.file.folder, "folder A") 
SORT file.name ASC 
```

```dataview
TABLE without id 
out AS "Uncreated files", file.link as "Origin", file.cday as "Created"
FROM "Inbox" or "Journal"
FLATTEN file.outlinks as out
WHERE !(out.file) AND !contains(meta(out).path, "/")
SORT file.cday ASC
```
