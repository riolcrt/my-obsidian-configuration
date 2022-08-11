#resource/enumeration

### Obsidian plugins reference
```expander
file:Obsidian tag:tech/plugin
```
 
- [[Obsidian Dataview]]
- [[Obsidian Local API Plugin]]
- [[Obsidian QuickAdd Plugin]]
- [[Obsidian Templater Plugin]]
- [[Obsidian Text Expander Plugin]]
 
<-->

## [[Obsidian Templater Plugin]]

This plugin is used in the templates creation phase. It allows us to create dinamic content based on different aspects of the notes, for example:

- It prompts data when a note is created and fill some boilerplate content with that data. 
- It feeds [[Obsidian Dataview]] and [[Obsidian Text Expander Plugin]] queries based on the file name or the current date.
- In the weekly notes templates, it fills a dataview query with all the daily notes that belongs to that week.


## [[Obsidian Dataview]]

This plugin is used also in the templates. It allows to display notes based on complex queries, for example:

- It allows to display witch notes were modified during a day in the daily template.
- It allows to display witch projects, resources or developments are mentioned during a week in the weekly notes.


## [[Obsidian QuickAdd Plugin]]

I use this plugin to create macros to automatize in part the workflow. It allows create macros to perform different actions when create a note and other options, like, capture.

### Capture data in your dailynotes when you are on another note.

I setup an action to capture data and add to the current day note including the hour, this way is easy to create a log for the day actions.

- [[Example - OSI - QuickAdd - Create a capture data to dailynote macro]]
- [[Example - OSI - QuickAdd - Create a template based note and add a link in place]]


## [[Obsidian Local API Plugin]]

Generates a local rest so it can be used to extract knowledge from outside of the application. It could be used for example to list all the technologies that are in our knowledge base and so on.

