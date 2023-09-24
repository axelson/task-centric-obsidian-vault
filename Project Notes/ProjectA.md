---
project-tag:  ProjectA
tags:
  - ProjectA
---
## Open Tasks
```tasks
tags includes ProjectA
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
TABLE ProjectA
WHERE ProjectA
SORT file.day DESC
```

## Completed Tasks
```tasks
done
tags include #ProjectA
```