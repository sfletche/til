TIL some of the ways JIRA can be configured...

Issue Types
- Bug
- Dev Task
- etc
Issue Type Scheme (e.g. OC: Kanban Issue Type Scheme)
- Used for configuring which Issue Types are present 
- Actions
    - Edit the Issue Types 
    - Associate with a Project 
    - Copy Issue Type Scheme


Workflows
- To Do -> In Progress -> Ready for Review -> etc
Workflow Scheme (e.g. OC: On Call Simplified Workflow Scheme)
- Actions
    - Add Status
    - Add Transition


Project is associated with one or more Workflow Scheme 
- (e.g. OC: On Call Simplified Workflow Scheme) -- Issues -> Workflow Schemes
- Project can be assigned a Workflow 
- Workflow includes Issue Types that will utilize this workflow (e.g. Research / Analysis and Bug)
Projects are also associated with an Issue Type Scheme that defines the Issue Types available for that Project
- e.g. see OC: Kanban Issue Type Scheme


Boards are configured for a Project
- e.g. On Call Management board 
Boards are configured with specific Issue Types via an Issue Type Scheme
- e.g. see OC: Kanban Issue Type Scheme



New Project / New Board (something like the following...)
- Copy existing Issue Workflow Scheme and Rename
- Add one or more Workflows (themselves copied from one of the SDPT Workflows)
- Add Workflow Scheme to Project
- Copy existing Issue Type Schema and Rename
- Associate Issue Type Scheme with Project 
- Configure Issue Type Schemes 
- Configure Workflows 
- Create Board for Project / Configure Columns
