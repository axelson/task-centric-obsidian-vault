<% "---" %>
project-tag: <%* const projectTag = await tp.system.prompt("What is the project tag?", "", false, false) %> <% projectTag %>
tags:
  - <% projectTag %>
<% "---" %>
## Open Tasks
```tasks
tags includes <% projectTag %>
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
TABLE <% projectTag %>
WHERE <% projectTag %>
SORT file.day DESC
```

## Completed Tasks
```tasks
done
tags include #<% projectTag %>
```