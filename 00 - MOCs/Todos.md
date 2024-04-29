
```dataview
task
where contains(list(" "), status)
where text !=""
group by file.link
sort date(file.cdate)
```
