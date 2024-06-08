breakdown into three dataview queries that have a to do by heading in each journal note (one for ideas, one for insights and one for to-dos).
# List of task types and count
```dataview
TABLE WITHOUT ID key as Tasks, length(rows) AS Total, length(filter(rows.tasks, (r) => r.completed)) AS Completed FROM "Journal" or #Journal FLATTEN file.tasks as tasks GROUP BY tasks.text SORT length(rows) DESC
```
# Which note contains which tasks

```dataview
TABLE file.tasks.text AS "Tasks", file.cday AS "Created"
FROM "Journal" or #Journal  
FLATTEN file.tasks as T
WHERE !checked AND file.cday >= date("2023-01-01") 
```
