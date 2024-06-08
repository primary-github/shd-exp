# Notes Which Need Work (I have it set to 2023 only)
Shows all vault to do, can limit by date

This is a list of all tasks that haven't been marked complete within the vault. Narrow as need be
```dataview
TABLE file.tasks.text AS "Tasks", file.cday AS "Created"
FROM "" 
FLATTEN file.tasks as T
WHERE !checked AND file.cday >= date("2023-01-01") 
```


# List of task types
```dataview
TABLE WITHOUT ID key as Tasks, length(rows) AS Total, length(filter(rows.tasks, (r) => r.completed)) AS Completed FROM "" FLATTEN file.tasks as tasks GROUP BY tasks.text SORT length(rows) DESC
```