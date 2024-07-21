# Concept Notes Which Need Work

```dataview
TASK
FROM #concept
GROUP BY file.name
```

[[Dataview reports/all-vault-to-do]]

# Notes in Inbox and Journal

The notes below need processing. The inbox 

```dataview
TABLE tags, file.ctime AS "Created"
FROM "Inbox" OR "Journal"
where file.tasks != incompleted
SORT file.cday DESC
```

# Table of Concept Notes and when They Were Last Maintained

```dataview
TABLE last-maintained
FROM "Research" and #concept 
```
