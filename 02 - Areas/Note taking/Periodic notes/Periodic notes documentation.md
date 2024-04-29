---
aliases:
  - Periodic notes documentation
---
up:: [[01 - Building a Second Brain|Building a Second Brain]]
___
# Periodic notes
Obsidian is excellent for writing chronological journals, and taking advantage of the [[Templates]] and [[Community plugins]] capabilities I have organized a lot according to my daily notes which are in turn aggregated into my weekly notes go help get an overview of the happenings during the week. I have plans to do this for monthly and yearly notes as well. 
I tend to use the calendar plugin to create or access the daily and weekly notes. 
## Daily
[[Daily template]]
## Properties
The daily note has in its [[Obsidian Properties|Properties]] an automatic link to the weekly note using the *Parent-date*. 
There is also the date the note is created. 
tags for assigning the type.
Aliases  allow for other notes to reference this note using a different name, I have another date format following YYwWWd format. 
## Sections
For work I have implemented a button using the [[Meta bind]] plugin that will trigger the creation of a new meeting using the [[Meeting template]] and another button for creating inbox notes (fleeting notes) [[Inbox note template]]. The inbox notes are mainly used for quickly capturing ideas or topics etc. see [[1 - Capture|Capture]]. 

There is also a fun daily quote template fetcher. 

Next I fetch the tasks created in the weekly note using a [[Dataview]] query. 

Next I have a section for the day's top three priorities and Brain dump. This has helped me a lot with both keeping track of what to do so I don't get distracted. I implemented this following the recommended method in [[Harvard timeboxing]].

Then there's the summary section. This is where the inline properties are used to aggregate up to the weekly note. By writing a property followed by dual colons it becomes an inline property that can be picked up by a [[Dataview]] query. For example, SUM or POS. To make it look nice I used the [[List callouts plugin]]. 
### Meetings
As mentioned above there is a button for creating a note and applying the meeting template (in which a command is run to move the file). These meetings are then picked up by the dataview query for meeting notes in the daily note and the weekly note.

Below that there is also a section for aggregated todos from the meetings for that day. 
## Weekly
[[Weekly template]]
The weekly note is used for three main reasons. 
1. Create tasks that should be prioritized during the week.
2. Give an overview of what is to come and what is currently being worked on on a higher level than the daily note. 
3. A space for reflection to make it easier for later reflection on a larger scale without having to dive too deep into details. 

The idea is that the daily notes are distilled by writing summaries which are aggregated using inline properties. The weekly note can then in turn distill those highlights further and highlight achievements and challenges. See [[3 - Distill|Distill]] from the [[0 - CODE Method|CODE Method]]. 

The todos are also managed a bit differently than the daily note. The weekly note's todos section is meant to help the user when they go back in time and reflect to see what tasks where created and closed during that week. It is done in this way because tasks created during a week are not necessarily completed the same week. (note this requires the [[Tasks plugin]])

There is also the option to see each of the weeks meetings according to day and from those meetings there is also a summary of the people interacted with in meetings. 
## Monthly
TBD

## Yearly
TBD

# References
