All notes in literature-notes folder with university tags and unchecked check boxes.

These notes could mostly be considered phase two of the workflow.

```dataview
TABLE tags, file.tasks.text AS "Tasks", file.tasks.checked AS "Completed?"
FROM (#university-reading OR #university-lecture) AND "Areas/literature-notes"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
SORT file.cday ASC
```
