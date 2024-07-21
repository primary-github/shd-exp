Hopefully this should give indication as to the purpose or connection evidence has to other notes. 

# All literature notes
```dataview
TABLE file.cday AS "Created", file.inlinks AS "References", file.outlinks as "ideas contributed"
FROM #literature-note OR #literary-poetry OR #literary-fiction OR #literary-philosophy 
WHERE file.name!="tag-taxonomy"
```
# All video notes
```dataview
TABLE file.cday AS "Created", file.inlinks AS "References", file.outlinks as "ideas contributed"
FROM #video-note 
```
