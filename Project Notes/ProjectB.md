---
project-tag:  ProjectB
tags:
  - ProjectB
---
## Open Tasks
```tasks
tags includes ProjectB
priority is not high
not done 
```
## Documentation

## Meeting History
```dataview
LIST
FROM "Meeting Notes"
WHERE contains(file.tags, this.project-tag)
SORT file.day desc
```

## Status Notes
```dataview
TABLE ProjectB
WHERE ProjectB
SORT file.day DESC
```

## Completed Tasks
```tasks
done
tags include #ProjectB
```