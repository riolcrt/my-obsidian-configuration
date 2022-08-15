#note/daily 
<%* 
let fileTitle = await tp.file.title
%>

<< [[<% tp.date.now("YYYY-MM-DD", -1) %>]] | [[<% tp.date.now("YYYY-MM-DD", 1) %>]]>>


## Summary
So.. today...

## Tasks
### Incoming 
```tasks

not done

due before <% tp.date.weekday("YYYY-MM-DD", 6) %>

```

### Due Today
```tasks

not done

due <% tp.file.title %>

```

#### Done Today
 

```tasks
done on <% tp.date.now("YYYY-MM-DD") %>
```


### Files where tasks were done
```expander
task:"✅ <%fileTitle%>"
```
 
 
<-->

### Meeting Log
```expander
file:<%fileTitle%> tag:note/meeting 
```
 
 
<-->

### Notes Modified
```dataview
LIST FROM "" WHERE file.mtime >= this.file.ctime AND file.mtime < this.file.ctime + dur(1 day) SORT file.name
```