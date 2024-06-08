All of the individual atomic ideas within this vault. This should make it easy to detect ideas that aren't being used (maybe need development) or they have no evidence in which case this should be a pointer for me.

```dataview
TABLE file.cday AS "Created", file.inlinks AS "References", file.outlinks AS "evidence"
FROM #idea 
WHERE file.name!="tag-taxonomy"
```