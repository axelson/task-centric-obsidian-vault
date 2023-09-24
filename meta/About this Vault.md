This vault tries to capture the workflow described in this reddit post:
https://www.reddit.com/r/ObsidianMD/comments/16psegl/how_i_manage_tasks/
- [[Original Reddit Post Contents]]

Plugins and how they're used:
- https://github.com/farux/obsidian-auto-note-mover
	- moves templated notes for People and Meetings into their folders
- https://github.com/logancyang/obsidian-copilot
	- easy access to GPT and help using Tasks, Templater, and Dataview
- https://github.com/obsidian-tasks-group/obsidian-tasks
- https://github.com/SilentVoid13/Templater
- https://github.com/blacksmithgu/obsidian-dataview

## Notes
Folders directly mentioned
- People
- Meetings
- Emails

Folders I've added
- Daily Notes
- Project Notes

Plugin settings changed
- Templater
	- apply template on file creation

Tags in meeting notes are used to link the meeting note to the project page, they also link tasks to the project

Project "tags"
- A project has both a tag and a property, e.g. it may have #ProjectA but also have
- ProjectA:: Some content about Project A

Decisions I made
- Use Tasks default task format instead of dataview format (easier to write/read)
- Create an `Attachments/` folder for all attachments
- Set up folder templates with the Templater plugin

This workflow reminds me of this other task centric vault