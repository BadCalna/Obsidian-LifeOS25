---
tags:
  - TaskManagement
Date-creation: 2025-03-09 15:52
Date-modified: 2025-03-09 15:52
---
> [!important] ## Topic 
- Follow the master of Notion to build a task management system.

>[!example] ## Action and its thoughts
- TF used three main database
	- A task database (using the Notion Task Database Feature)
	- A task journal database
	- A project database

### Task Database
---
- Notion Task Database originally have those attributes
	- ***Name
	- ***Assignee
	- ***Due Date
	- ***Status(a special select, have a default item)
- **Specially**, TF add an attribute that is ***Priority***
	- The priority is a special status that can set default value as well.(Medium as default)
- A New concept, ***Smart List**
	- It's an flag to mark those **someday tasks**
	  which means: ==tasks that wanna brain dump out of my head, and know for sure that wont do it right now==
- Some common attributes: ***Created Time***, ***Last edited Time***
> [!important] Important Attribute
>  - ***Project***
>    A relation between tasks and project
>  - Tips: The relation attribute have a default value of the item **Limit**, that is the place you control the relationship between two databases, such as: 1-1, 1-N, N-N. In this example, the relation between task and project should be ==1(project) - N(tasks)==
---
 
#### Pro tips: Layout Customized
---
- Above are about the database, then TF turn to each tasks page and adjust theirs layout 
![[Pasted image 20250309162150.png]]
- He pinned several most use attribute into the Heading parts
	- Status
	- Due Date
	- Project
- And what is useful is that he want to open a task and jot down some notes right after open the page==「Exactly what I wanna do」==, so he drag the attributes group to the Panel part
- What's more, you can edit the attributes group in the panel too!
![[Pasted image 20250309162726.png]]
- You can add section as TF do: add a General Properties section
	- And add a "Helper Properties" section as well for those attributes not related to the task itself but some other usage
	  eg. In my design, there are some properties are set for data collection, further data analysis and calculations.
	- TF add a formula attribute called "Meta Label", a handy little property for showing an icon or emoji based on the state of the task
	  **To fast identify those recurring tasks or overdue tasks -- which is good and ==can cut off my overdue reminder==    ^700540
- Then comes to "make this prettier" part
	- TF mentioned that the status value "Doing" is not usually used, so he use a trick to make the status present as a checkbox and minimize its width just as I do with "Completion" for now
- Then for more views
	- Done view to show those tasks been done
	- Calendar view(Actually don't see that coming.. I thought it is completely useless for me before I watch and just write down for now)  
	- ==hmm.. Turns out to be a traffic leading to other videos about Notion Calendar App and Google Calendar, maybe next time

####  The Ultimate Tasks page that can use for everyday work
---
  -  TF creates a list view called **Inbox** -- a default place to dump tasks come into ur life
	  - list view, shown some properties, use the checkbox trick
	  - TF mentioned that in his system, **Inbox can only be cleared in following three ways**
		  - ***Finish a task***
		  - ***Delete a task**
		  - ***Move it to the right Project*** 
		  - So he use the filter to hide those task which is done or have related project or is a someday task(**means not for now**)
  - Now it's the **Today** view, since the properties setting above, now u can just duplicate the view be done just now.
	  - Just change the filter
		  - Tips: a date in Notion can be divided into start/end date, so remember set the end date as the filtering properties.  
		    ==But actually I don't use start/end date, let's see how TF make use of it==
			  Tips for tips: if u don't set a date range, the start date will be the same to the end date. 
- **Week** view is a calendar view, only two properties will be shown except the Name: Project and Status
-  **Scheduled** view is a view that list all tasks that have a Due.
	- Here comes a usage of *group* : which can aggregate items that fits the group rules
- **No Due**:  view that show no due date tasks. Noticed that the **Inbox** also show those undue tasks, but thinking the filter condition, as long as the task is linked to a project, then you will never find it in **Inbox**. ==That is why we set this view==.
- **By Project**: This view shows the tasks under certain project. 
	- First add some sample projects.
	- Then group by project, and set the sort manually
- **All & Done**: Easy to understand what's it for

### Project Database
---
 - **Status**
	- *Planned*
	- *On Hold*: kind of like "suspended"
	- *Ongoing*: a project that runs in a very long period, like family maintenance 
	- *Doing*
	- *Done*
- **Archived**: A checkbox
- **Edited, Created**: exactly the same to properties in Tasks who has a same name
- **Progress**: A formula property to show the completion of the Project tasks
	- 
#### Pro tips again: Layout Customized
---
like above
#### Project ***view***
---
- **Active**: Filter those projects whose category in the doing phase, of course Unarchived
- **Planned**: Specific status projects, show properties of status(for easily change the status)
- **Board**: A kanban view, group by status
- **Archived**: Cuz nowhere to see this status project

#### Database **Template**
---
- Create ourselves a template
- First a task view with a self-referential filter
  The Project template have will related to the creating project while using this template to create the project page
> [!Tips] A little Trick
> First TF build a page based on empty database **Task Journal**, and add a property called "Date"
> Then he start to edit the template of **Task Journal**.
> 	First print @ at the title and @Today
> 	Second he edit the property "Date" to the select 'Today'
> 	And here comes the smart journal template!
> 	![[Pasted image 20250315143508.png]]
### Recur Tasks
---
- TF add some properties in a new Group "Recurring Tasks Properties"
### Task Journal Database
---
> [!tips] You can link to different database in a page 



> [!Tips] ## Key takeaways
- 

> [!note] ## Video Link
[UltimateTasks](https://www.youtube.com/watch?v=H2IFv_GBdUQ&t=294s)
