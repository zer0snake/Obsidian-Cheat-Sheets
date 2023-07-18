# Dataview Plugin

Overview of Dataview plugin commands

![Dataview Documentation](https://blacksmithgu.github.io/obsidian-dataview/)

## Order of Operations

1 FROM
2 WHERE
3 SELECT (table,task,list,calendar)
4 SORT
5.1 FLATTEN
5.2 GROUP BY
6 LIMIT

## LIST
- List from entire vault
```dataview
LIST
FROM ""
```
- List a specific filename
```dataview
LIST
FROM ""
WHERE file.name = "Untitled"
```
Can write **one** piece of metadata after list
```dataview
LIST file.ctime
FROM ""
WHERE file.name = "Untitled"
```
## Table
Can use a path in FROM
```dataview
TABLE file.ctime, tags
FROM ""
WHERE file.name = "Untitled"
```
- From entire vault
```dataview
TABLE file.ctime, tags
FROM ""
```
>[!note]
>Tag should be in YAML frontmatter

## TASK

```dataview
TASK
FROM ""
WHERE file.name = "Untitled"
```

- See all tasks that are not completed
```dataview
TASK
FROM ""
WHERE !completed
```
- Group tasks by file
```dataview
TASK
FROM ""
WHERE !completed
GROUP BY file.link
```

## CALENDAR
Needs a date and time field to function
```dataview
CALENDAR file.mtime
FROM ""
```
```dataview
CALENDAR file.mtime
FROM ""
WHERE tag = "test"
```
