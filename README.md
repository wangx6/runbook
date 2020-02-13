# VHI frontend Software Development
OVERVIEW
- [Scrum](#Scrum)
  - principals
  - board
  - stories/acceptance criteria/task
- Version Control
- Pull Request
- Coding Principals - simple and consistent
- Testing
- Deployment
- Environment

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
```As a user   
I want to have my inputs validated  
So that the system can store my information correctly and inform me in a graceful manner if I made any mistakes.    

Details:  
1. when I navigate to application form on a PC and I click the submit button.  
If the “name” is empty I should see a message popup saying the “the name input can not be empty”  

2. If the “name” length is more that 110 chars I should see a message popup saying the “the length of the name exceeds the limit”  

3. If the validation of any input is doesn’t not pass the page should automatically scroll to the position of the first input that does not pass the validation and highlighted in red and the error message will be displayed to the right of the input```

## Acceptance Criteria
```Given that I have open the app  
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

…```


