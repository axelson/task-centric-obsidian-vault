Little background on what I use Obsidian for, as this greatly impacts my workflow and the rational for why I've set up Obsidian the way I have.

I am a IT Director at a Fortune 500 company, so my role is very much based around maintaining visibility onto many projects, what my teams are working on, and the relationships between people, projects, and tasks. The main purpose of my Obsidian vault is to capture notes from meetings, take action items and surface them in my 'Task Dashboard', Daily Note, and Project Notes. I'll walk you through each of them, their purpose and how I use them. 

_Quick note_ - My system uses 'Auto Note Mover' (moves templated notes for People and Meetings into their folders), 'Copilot' for easy access to GPT, Tasks, Templater, and Dataview. 

**Daily Note** - Pretty standard daily note. I use the templater plugin. I have the following sections:

- High Priority Tasks - This section brings up my high priority tasks using the Tasks plugin and this code. I only mark tasks as high priority if they are a "I gotta do this today" 

````
```tasks
priority is high
not done
```
````

- Back and Forward links - 

```
[[<% tp.date.now("YYYY-MM-DD", -1) %>|Yesterday]]
[[<% tp.date.now("YYYY-MM-DD", +1) %>|Tomorrow]]
```

- _New Tasks_ - This is where I create new tasks that aren't generated from a meeting. I have a blank task in my template just so I have a starting point and don't have to type out the markdown. 
- _Other Notes_ - Random scratch pad for things that happen during the day. 
- _Meetings Attended_ - This is my home base for new meeting note creation. At the start of the day, I create a link to every meeting that I'll be having. It allows me to level set and plan my day. When the meeting starts, I click the link and it creates the meeting note. I'll then apply my meeting template to it. 

​

```
ex. [[2023-09-22 Marketing Staff Meeting]]
```

- Tasks Completed - This captures all the tasks that I complete in a day so I have a log of what I did. I don't find this very useful, but it sits at the bottom and doesn't take any effort, so I leave it. 

​

````
```tasks
done on {{date:YYYY-MM-DD}}
```
````

**Meeting Note** - This is the lifeblood of my obsidian vault. I attend a lot of meetings and generate a lot of action items, follow-ups, status updates, etc. Pending the type of meeting. I use the same template for all types of meetings except 1:1's with my team members. For those, I use the note for the individual. Every person that I work with or attend meetings gets their own note so that I can easily cross reference everything I have done with them. 

My meeting note is pretty simple: 

- _Attendees_ - List of everyone in the room, linked to their people note. Most people don't even have a page, as I have no reason to create it, but if I ever do, it'll automatically be linked to all the back links of meetings that we've attended together. This helps me when I am dealing with departments that I don't meet with a lot so I can remember the context of what we've needed to meet on in the past. 
- _Conversation_ - I put my meeting notes in here. I type quickly, so my notes are often verbatim. This allows me to copy paste them into CoPilot (plugin) and allow ChatGPT to summarize the meeting into a paragraph or two of main topics. Sometimes I'll do this if the meeting was long or important, but it's not a major part of my workflow yet....still in the testing phases there. I'm careful not to name my company or leave PII in what I submit to GPT. 
    - Inline Tags - If there's something that's really important...a status update, a key quote that someone says, or something I want to take note of, I use an inline tag. I always match my inline tags to a tag that I use for a Project name. Typically, I'll use the '#' and find the tag and then just delete off the '#' and create the tag. This is really important to allow me to pull together information into my project notes, which I'll cover next. 

​

```
ProjectA:: Important content to remember goes here...
```

- _Tags/Links_ - This is where I connect the content of the note to projects that I am working on. Sometimes I don't have links, but other times, the meeting directly relates to a project. I just use tags for my Projects that I have notes for. I'm careful with the use of tags and don't make them willy nilly. Every tag has a purpose. 
- _Action Items_ - More often than not, I'll put any action items from a meeting at the end of the note in this section. If it's a very long meeting with a lot of notes, sometimes I'll put them in the 'Conversation' section, in-line with where the task was generated in the conversation, but more often than not, it goes into the 'Action Items' section. I don't like to fuss with a lot of due dates and alarms on tasks...I keep it simple. My tasks look like this...

​

```
- [ ] #ProjectA Call [[Joe Smith]] to talk about [[Project A]]. 
```

I'll put whatever context I need into the task, but really, the important thing is that every task has a tag that tells me the bucket of work that it belongs to so that when I am working through my task list, all tasks are grouped together and it allows me to easily see what projects I am falling behind on. 

**Task Note** - My task note is the clearing house for all that tasks that I have created that are still pending. It's blocked out by tag for each project. 

_High Priority_

````
```tasks
priority is high
not done
```
````

_Project Tasks_

````
```tasks
tags includes #ProjectA 
priority is not high
not done 
```
````

_Everything Else -_ I have a section at the end that catches any tags that are used that don't have projects associated with them. I also have people specific tags that I use for my direct reports and my manager so that as items come up that I want to discuss with them for our 1:1's, I just use their specific tag and it goes into a list in their personal note. Those few people are treated like a project, so I don't want their items to be included here, as they are things to talk about, not tasks to be done. 

````
```tasks 
not done 
description does not include canceled 
path includes daily
tags does not include #ProjectA
tags does not include #ProjectB
tags does not include #ProjectC 
tags does not include #Joe
tags does not include #Tom
tags does not include #Larry
priority is not high
sort by tag
no due date
``` 
````

**Project Notes** - Project notes serve to pull together all the information that I generate from attending meetings, meeting with my stakeholders and peers. They allow me to have a single page glace at everything that goes on around that project. They are broken down into the following sections: 

_Open Tasks_ - Collection of tasks for this project. Simple duplication of what's in the Tasks Note. 

_Documentation_ - Links to related notes, documentation, emails, etc. I should probably automate this to pull in any tags for the project that aren't in my Meeting Notes folder. My project notes workflow is the most recent addition, so it still has room for improvement. 

_Meeting History_ - List of all meetings that have the project tag. This is super helpful for my world, as I am constantly needing to go back and see note from meetings related to specific project decisions. It makes my meetings notes 10x more valuable and discoverable without needing to use a search bar. 

````
```dataview 
list
from #ProjectA and "Meeting Notes"
sort file.day desc
```
````

_Status Notes_ - This is where I surface my in-line tags into a nice table view. With a simple in-line tag, anything I've tagged related to that project shows up. Where this is really nice is when I take our weekly status report, I'll save the email in Obsidian in my Email folder, and I'll quickly toss in the in-line tags next to each update. This allows me to see, week by week, the status update for each project. 

````
 ```dataview 
table ProjectA
where ProjectA
sort file.day desc
```
````

_Completed Tasks_ - List of all completed tasks for a project. 

````
``` tasks
done 
tags include #Experimentation
```
````

​

My workflow for the day starts with opening Obsidian and generating my Daily Note. I quickly add any meetings from my calendar into the day's list of 'Meetings Attended'. I then work through my 'Priority Tasks' at the top of my daily note. 

As I attend a meeting, I click the meeting link and the note is generated. I then apply the 'Meeting Note Template', enter the attendees names into the 'Attendees' list, and enter any applicable project tags. As the meeting goes on, I take my notes, creating any to-do tasks with a tag at the start of every one to denote the related project. If it's high priority, I'll mark as such. 

When I'm not in a meeting, I'm working through my task list, bouncing between priority projects. I also have a master list of all my Projects that's a bit more manual than I would like, but I find that maintaining it allows me the presence of mind to capture completed projects, wins, milestone dates, and that kind of thing. 

I was a 10+ year Evernote user and Obsidian completely changed my perception of what a note taking application could be. I don't get into the PMK or second brain stuff, but Obsidian is far better as a task application than anything I have found, as it pulls together my schedule, meeting notes, tasks, and people management into a single neat tidy package. I've still got a lot to do to improve. I've only been using it for about 6 months, but I'll never go back to Evernote. 

Hopefully my process will inspire some people out there to give Obsidian a try as a task manager.