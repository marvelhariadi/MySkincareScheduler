# Skincare Routine Planner

## Description:
### _What will the application do?_
This program schedules the user's skincare routine for a week. The main screen has seven slots, representing the seven days of the week. The user can click on each slot to plan out and view their skincare & haircare regimen for the day. In each day-of-the-week slot, the user can create a "morning" or "night" routine. The user can view and plan out which products they intend to use for the day, when they want to use it (in the night or in the morning), and in what order. The user can also make changes to their routine for any day of the week at any time. Across seven days, this provides a handy beauty routine planner the user can refer to when doing their beauty routine.

### _Who will use it?_
Users interested in skincare, but struggle to keep a consistent routine. These users may often forget the products they are meant to use at various times of day and days of the week.  
 
### _Why is this project of interest to you?_
I like taking care of my skin. It is a therapeutic routine that enriches my life, and I know it does the same for many other people. But with my busy schedule, I sometimes struggle to remember which products I am supposed to use and when. I know many other busy people relate to this struggle, but still want to have a consistent skincare routine so that they can maintain their appearance. So I am making this project to address that need. 


## User Stories
- As a user, I want to be able to view my morning and night routines for each day of the week in the main screen. When I click on them, I can directly access my daytime and nighttime routines for the day. 
- As a user, I want to be able to add multiple skincare products to a routine. 
- As a user, I want to be able to delete skincare products from my routine as many times as I want
- As a user, I want to be able to reorder my skincare products in my routine as many times as I want
- As a user, I want to be able to save the entire state of the application (in this case: the skincare routine in each Routine object) to file
- As a user, I want tobe able to reload my skincare routine that I have previously edited from file and resume exactly where I left off

## Phase 4: Task 2 (Event log sample)
* Thu Aug 11 00:04:33 PDT 2022
* JSON file loaded
* Thu Aug 11 00:04:38 PDT 2022
* Skincare product added to routine: Monday Morning
* Thu Aug 11 00:04:41 PDT 2022
* Skincare product added to routine: Monday Morning
* Thu Aug 11 00:04:42 PDT 2022
* product selected
* Thu Aug 11 00:04:50 PDT 2022
* IndexOutOfBoundsException thrown
* Thu Aug 11 00:04:53 PDT 2022
* product selected
* Thu Aug 11 00:04:56 PDT 2022
* product selected
* Thu Aug 11 00:04:57 PDT 2022
* product reordered in routine: Monday Morning
* Thu Aug 11 00:05:01 PDT 2022
* Skincare product added to routine: Sunday Morning
* Thu Aug 11 00:05:04 PDT 2022
* product selected
* Thu Aug 11 00:05:06 PDT 2022
* product selected
* Thu Aug 11 00:05:06 PDT 2022
* product deleted in routine: Sunday Morning
* Thu Aug 11 00:05:08 PDT 2022
* JSON file saved
* Thu Aug 11 00:05:10 PDT 2022
* program exited


* Process finished with exit code 0


## Phase 4: Task 3 (UML Diagram Reflection)
You might notice in my SkincareRoutinesGUI class (this spawns the main screen of the program) as well as the RoutinesOverview UI class that I have 14 JSON files that must be instantiated in order for my program's persistence to run correctly. It represents 14 skincare Routine objects (one for every day of the week, morning and night). 14 is a lot of JSON files. Provided more time and help I would have liked to merge all these JSON files into 1 file. The single JSON file would host a list of 14 Routine objects, which would in turn host a list of skincare product objects. This nested-list structure would require me to refactor my JsonReader and JsonWriter files greatly. I tried to do this during Phase 2, but it was too hard. But if I was successful, this would greatly simplify my UI code as well as reduce redundancy. 

I would have also liked to refactor my GUI in a way where the pop-up GUI classes (EditProductGUI, ReorderProductGUI, SelectGUI) all extend a common abstract class, since they share many similar methods. But I could not since these classes all already extend JFrame. What I could have done was maybe create a super abstract class called "GUI" that extends JFrame and made all my current GUI classes extend GUI. So all my current GUI classes still have access to JFrame methods, and also any methods I would put in the GUI abstract class. This would reduce my redundancy greatly.
