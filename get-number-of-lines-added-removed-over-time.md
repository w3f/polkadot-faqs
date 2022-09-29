Use git log to find the two commits you want to compare (e.g. the last and first of the month - so for August, 5370f9686c190264d7c6a761a184f0058f73bc82 is the last and e75c1f0ea4b1824c38b4686ee16dddba88ed0fff is the first)
Now type git diff COMMIT1 COMMIT2 FILENAME, e.g. git diff 5370f9686c190264d7c6a761a184f0058f73bc82 e75c1f0ea4b1824c38b4686ee16dddba88ed0fff ./all.json
This will include ALL changes made as well as some formatting information, so we want to ignore those
So we grep for just those lines starting with + or -, but ignore lines starting with +++ or --- because those relate to files. Then we count up the number of lines since 1 line = 1 change

```
git diff 5370f9686c190264d7c6a761a184f0058f73bc82 e75c1f0ea4b1824c38b4686ee16dddba88ed0fff ./all.json | grep "^[-+]" | grep -v "^+++" | grep -v "^---" | wc -l
```

and that gives us

1369 lines added or removed in all.json

but if a line is CHANGED, note that it will be shown as both "added" and "removed" (because you're "removing" the old line and "adding" a new one with different text)