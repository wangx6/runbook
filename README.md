# VHI frontend Software Development
OVERVIEW
- [Scrum](#Scrum)
  - [Scrum Principals]Scrum Principals
  - [Scrum Board]Scrum Board
  - [Story]stories
  - [Acceptance-Criteria]Acceptance Criteria
  - [Tasks]Tasks
- [Version-Control]Version Control
- [Pull-Request]Pull Request
- [Coding-Principals]Coding Principals - simple and consistent
- [Testing]Testing
- [Deployment]Deployment
- [Environment]Environment

## Scrum
### Sprints  
2 or 3 weeks ( 10 – 15 working days, 60 to 90 working hours )      
### Scope and seek – define stories and details of each story  
- Input – business requirement  
- Output – stories and stories details  
- Who – UX, UI, PM and SM  
Note: stories must be specified and grouped before any sprints start  
### Stand-up  
- What have you done yesterday and what do you plan to achieve today  
- Any blockers or concerns  
### Refinement  
- Who – QA, BA, DEV  
- Input – stories for the next sprint  
- Output – acceptance criteria which describe all details of a story    
**IMPORTANT**: stories must be ready and signed off. Time management is crucial to make sure all the ACs are defined by the end of this meeting. Keep discussion of the story to minimum. The focus of to create ACs.
### Planning  
- Time – the day before the sprint. (Yes, the whole day)  
- Who – QA, Dev  
- Input -- acceptance criteria  
- Output – technical tasks with estimated time in hours (6 hours per day)  
### Code freeze  
- When – 2 days before the end of sprint  
- Purpose – prepare for the demo  
- Action – freeze the code as much as possible.  
- Exceptions – any modification must be discussed.  
### Demo  
- Who – every team member  
- Env -- pre-prod    
### Retrospective  
- Good
- bad
- nice-to-have	  

### Stages
- __Next__ - dev
- __In progress__ – dev
- __PR__ -- dev
- __Dev__ done -- dev
- __QA__ – only QA have the permission to drag a ticket into the this column
- __Done__ – only QA have the permission to drag a ticket into this column


## Story
```
As a user   
I want to have my inputs validated  
So that the system can store my information correctly and inform me in a graceful manner if I made any mistakes.    

Details:  
1. when I navigate to application form on a PC and I click the submit button.  
If the “name” is empty I should see a message popup saying the “the name input can not be empty”  

2. If the “name” length is more that 110 chars I should see a message popup saying the “the length of the name exceeds the limit”  

3. If the validation of any input is doesn’t not pass the page should automatically scroll to the position of the first input that does not pass the validation and highlighted in red and the error message will be displayed to the right of the input
```
## Acceptance Criteria
```
Given that I have open the app  
And I navigate to the application form page  
When I click on submit button  
And the name is empty   
Then the popup will be displayed  
And the message in the popup is “the name input can not be empty”  


Given that I have open the app  
And I navigate to the application form page
When I click on submit button
And the name is one or more spaces 
Then the popup will be displayed
And the message in the popup is “the name input can not be empty”
```
## Task
```
Create input validator layer in the data model and the returned result should contain the property name and the correct error message – 4 hours
Unit test the validator with required scenarios – 2 hours
Trigger popup component if the validation failed – 1 hour
Highlight the input box and display the error message at the right of the input. – 3 hours
Scroll the window to the first input that contains error. – 3 hours
```

## Version Control
All branch names are in lower case. Examples:

```feature/pccs-201-create-pop-up-component```  
```bug/pccs-301-pop-up-not-showing-up-when-request-fails```  

```Feature branch – task level```  
```Fix branch – fix during QA phase```  
```Bug branch – bug found at Prod phase```  
```Dev branch – dev branch and only dev branch goes into QA env```  
```Release branch – test, test, test, test, test then if happy, merge it into master```  
```Master branch – master and only master branch goes into pre-prod and prod```  

## Pull Request
- What is the PR about?
- Why this PR exist?
- If you have left some legacy, why?
[]Include the story link and the task link
[]check CI
[]Only handling events in the controller
[]Business logics stays in the data model
[]complexity analysis
[]No business logics in the view
[]Unit test all functions
[]Intergration test all features


