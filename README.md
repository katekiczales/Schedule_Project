# Schedule_Project
*Note: this project was completed in April 2020 as part of a software construction class*

This application will allow its users to create a schedule reflecting their classes, then attach links to each class, 
allowing them to be accessed easily. This application is designed for students, particularly those in university. 
It is especially, though not exclusively, useful while school is primarily online during the COVID-19 pandemic. Students
may struggle to organize their classes, especially when each uses different websites. This tool would not only allow 
them to display the times and days of their classes, but to attach the appropriate links to each one. A student could 
look at the application, see that they have CPSC 210 the next day, and click on the attached edX link. Alternatively, 
had they attached both the edX and 210 homepage to the class, they could choose which one they wish to go to.

Further describing the application's features, it will *allow users to*:
- Add classes reflecting their **course schedule** (i.e. multiple classes and times)
- Display this schedule 
- Add multiples **links** to each class
- By choosing a particular class, select which (if there are multiple) link(s) they wish to go to                                                                 

This project is of interest to me because of my personal experiences. 
Going to university for the very first time while it is online has been a somewhat overwhelming experience. I have 
struggled, particularly at the beginning of terms, to manage my new classes. Oftentimes, each will have several websites
that it uses, and many of them are different across classes. While I use a scheduling tool to organize my lectures 
and lab times, one thing I have always felt was missing is the ability to add links directly to the classes on my 
schedule. As it stands, I will look at my schedule to see what I need to be doing, then go to my Google bookmarks or 
search for the website I want. Combining these functions in a single application is the logical progression of this. 
My firsthand experience as a student during COVID-19 leads me to believe that this will be a useful application, 
certainly one I can picture myself and other students using.

## User Stories

- As a user, I want to be able to add a class to my schedule
- As a user, I want to be able to add specific class times to classes in my schedule
- As a user, I want to be able to remove specific class times from classes in my schedule
- As a user, I want to be able to remove a class entirely from my schedule
- As a user, I want to be able to view my schedule
- As a user, I want to be able to add multiple links to a class
- As a user, I want to be able to remove particular links from a class
- As a user, I want to be able to view which links are attached to each class
- As a user, I want to be able to save my schedule to file
- As a user, I want to be able to load my schedule from file

## Refactoring: possible change to class hierarchy and code

- A few of the Tool subclasses contain similar or identical classes, each of which work in sequence to accomplish a 
task specific to that class; had I more time, I would extract these to reduce duplication. 
    - For example, the AddTimeTool 
and RemoveTimeTool would use the same classes (ClassText, DayText, and TimeText in sequence), except each would call a 
different function once these classes acquired necessary information (i.e. addTime() or removeTime()). This can be 
applied to most of the Tool subclasses. 
- The ScheduleApp has a field storing an ArrayList of SchoolClasses, which it passes to the abstract Tool class which 
then stores this in its own field. I would remove this field from the ScheduleApp, and only store it in Tool. 
- As is, there is duplication in the Tool subclasses; I would move this duplicate code into Tool's (super) constructor
