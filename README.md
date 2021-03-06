# Frontend Software Development
Simplicity and consistency is what we try to achieve.  
What we do should create value to our customer.  
What we do should make our team proud and happy.  

## OVERVIEW
- [Scrum](#Scrum)
   - [Scrum Principles](#Scrum-Principles)
  - [Scrum Board](#Scrum-Board)
  - [Story](#Story)
  - [Acceptance-Criteria](#Acceptance-Criteria)
  - [Tasks](#Tasks)
- [Version-Control](#Version-Control)
- [Coding-Principles](#Coding-Principles)
  - Factory
  - Service
  - Component
  - Model
  - Controller
  - View
  - Styling
- [Testing](#Testing)
- [Pull-Request](#Pull-Request)
- [Deployment](#Deployment)
- [Environment](#Environment)

## SCRUM
### Scrum Principles
#### Sprints  
- 2 or 3 weeks ( 10 – 15 working days, 60 to 90 working hours )
- Code freeze period will take up 2-3 days at the end of each sprint, hence, dev time ≈ 45 - 75 hours
#### Scope and seek  
Define stories and __DETAILS__ of each story. Details MUST be in place when a story is created 
- __Input__ – Business requirement  
- __Who__ – UX, UI, PM and SM
- __Output__ – Stories and stories details

:bulb:__IMPORTANT__
```
Stories MUST be specified and grouped before any sprints start  
```
#### Stand-up  
- What have you done yesterday and what do you plan to achieve today  
- Any blockers or concerns
- Keep it under 10 minutes
#### Refinement
- __When__ - Commonly once a week ane 1 hour per session. Time is crucial.
- __Input__ – Stories with details for the next sprint
- __Who__ – QA, BA, DEV
- __Host__ - BA
- __Output__ – Acceptance criteria which describe all details of a story 

:bulb: __IMPORTANT__
```
Stories must be ready and signed off. Time management is crucial to make sure all the  
ACs are defined by the end of this meeting. Keep discussion of the story to minimum. The focus of to  
create ACs.
```
#### Planning  
- __When__ – the day before the sprint. (Yes, the whole day)  
- __Who__ – QA, Dev  
- __Input__ -- acceptance criteria  
- __Output__ – technical tasks with estimated time in hours (6 hours per day)  
#### Code freeze  
- __When__ – 2 days before the end of sprint  
- __Purpose__ – prepare for the demo  
- __Action__ – freeze the code as much as possible.  
- __Exceptions__ – any modification must be discussed.  
#### Demo  
- __Who__ – Every team member and the business.  
- __Env__ -- pre-prod    
#### Retrospective  
- __What went well?__
- __What can be improved?__ 
  
### Scrum Board
- __Next__ - Only Dev has access to this column
- __In progress__ – Only Dev has access to this column
- __PR__ -- Only Dev has access to this column
- __Dev__ done -- Only Dev has access to this column
- __QA__ – Only QA have the permission to drag a ticket into the this column
- __Done__ – Only QA have the permission to drag a ticket into this column


### Story
```
As a user   
I want to have my inputs validated  
So that the system can store my information correctly.    

Details:  
1. when I navigate to application form on a PC and I click the submit button.  
If the “name” is empty I should see a message popup saying the “the name input can not be empty”  

2. If the “name” length is more that 110 chars I should see a message popup saying the “the  
length of the name exceeds the limit”  

3. If the validation of any input is doesn’t not pass the page should automatically scroll   
to the position of the first input that does not pass the validation and highlighted in red   
and the error message will be displayed to the right of the input
```
### Acceptance Criteria
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
### Tasks
__Task 0__  
```
Create input validator layer in the data model and the returned result should  
contain the property name and the correct error message – 4 hours  
```
__Task 1__  
```
Unit test the validator with required scenarios.  
Estimation: 2 hours  
```
__Task 2__  
```
Trigger popup component if the validation failed.  
Estimation: 1 hour  
```
__Task 3__  
```
Highlight the input box and display the error message at the right of the input.  
Estimation: 3 hours  
```
__Task 4__  
```
Scroll the window to the first input that contains error.
Estimation: 3 hours
```

## Version Control
### Naming convention
All branch names are in lower case.  
```
[type]/[ticket number]-[description of the branch]
```  

__Examples:__  
:x: Feature/pccs201-my-task  
:x: feature/pccs-202-my-task  
:x: bug/pccs202-My-task  
:x: fix/pccs202-my_task  
:heavy_check_mark: fix/pccs202-my-task   
:heavy_check_mark: feature/pccs201-my-task-with-brief-description  

 
### Type of branches you will need
- __feature branch__ – Task level
- __fix branch__ – Fix during QA phase
- __bug branch__ – Bug found at Prod phase
- __dev branch__ – Dev branch and only dev branch goes into QA env
- __release branch__ – Test, test, test, test, test then if happy, test it again, then merge it into master
- __master branch__ – Only master branch goes into prod

## CODING PRINCIPLES
- Data flow - One directional. How data format changes.
- Service - Singleton.
- Component - Everyting is a component. Including our universe.
- Model - Contains all business logic.
- Controller - ONLY detects event. Don't handle business logic in a controller.
- View - reflection of state which is created as side effect of static data from the model.
- Styling - Single source of truth(SSOT)

## CSS/SCSS  
### File Structure
All file names are in lowercase and multiple words are connected with "-"(hyphen).  
:x: sampleWrongName.scss  
:x: sample WrongName.scss  
:x: Sample-WrongName.scss  
:heavy_check_mark: _sample-correct-name.scss  
:heavy_check_mark: sample-correct-name.scss  
:heavy_check_mark: _sample.scss  
:heavy_check_mark: sample.scss  
- common  
   - _global.scss
   - _mixins.scss
- components  
   - _footer.scss
   - _header.scss
   - _spinner.scss
   - _confirm.scss
   - _product-list.scss
- pages  
   - _landing.scss
   - _application.scss
   - _checkout.scss
- index.scss  

### Naming Convention
- BEM
### Nesting style
:bulb: Try not to create to many layers. 2 is the prefered number.  
```css
.#{$global-namespace}-login-page{
  .form-btn{
    .submit{}
    .cancle{}
  }
  .#{$global-namespace}-form-input{
    .error{}
  }
}
```
### Responsive
```css
/* Mobile first please */
[class*="col-"] {
  width: 100%;
}
.#{$global-namespace}-form-page{
  padding: 10px;
}

/* For tablets: */
@media only screen and (min-width: 600px) {
  .#{$global-namespace}-form-page{
    padding: 50px;
    color: blue;
  }
}

/* For desktop: */
@media only screen and (min-width: 768px) {
  .#{$global-namespace}-form-page{
    padding: 150px;
    color: pink;
  }
}
```

## TESTING  
- Pre testing at PR stage – this may includes unit test, automation test, linting.  
- Unit testing – Both TDD and BDD. 
- TDD will test a function as a unit and does not deal with business logics directly. 
- BDD will test public function’s outcome which describes a business logic.

### Key knowledge you need to have
- Full scennarios covering
- Network async handling
- User event async handling
- Mocking implementation
- Mocking a module
- Cleanup
- Access an element within a component
- Access the content of a element
- Waiting for element to be ready  

__Example:__   
```javascript
// TDD
const queryApi = async (url = config.DEFAULT.LOGIN_API, payload) => await http.post(url)});}  

// TDD  
const checkEmptyStr = (str) => str.trim() === '';  

// BDD  
const validateLoginResponse = (res) => {  
        checkEmptyStr(res.data);  
        … other checks  
}  

// BDD
const userLogin =  async () => {
        const res = await queryApi(url, {}); 
        return validateLoginResponse(res);
}
```
- Automation test
- Penetration test
- Performance test – loading speed on different level of networks. Image rendering. Image size. Interaction responsiveness.
- Manual test
- Devices – test on all devices. Including portrait and landscape.
- Human perception test. Including loading speed, A11Y test.

## PULL REQUEST
Before a pull request is submited please paste the following template into your PR  
- What is the PR about?
- Why this PR exist?
- If you have left some legacy, why?

- Check list  
   - [ ] Include the story link and the task link
   - [ ] check CI
   - [ ] Only handling events in the controller
   - [ ] Business logics stays in the data model
   - [ ] Complexity analysis
   - [ ] No business logics in the view
   - [ ] Unit test all functions
   - [ ] Intergration test all features  
- BE NICE TO PEOPLE :relaxed:


## DEPLOYMENT
We use openShift to handle our deployment.  
- Pod naming convention
- Permission
- Deploy to multiple environment
- Deployment to QA environment - Dev lead, Test lead
- Multi-branch setup on Jenkins


## ENVIRONMENT
- __DEV__ – (example pccs-test.vhi.dev)
- __QA__ --  (example MULTIPLE – ie. pccs-test.vhi.QA-0-DEV)
- __PRE-PROD__ – (example pccs-test.vhi.pre-prod)
- __PROD__ 

## AUTHORS
Xin Wang (Principles  Software Engineer) - xin.wang@vhi.ie  
*"The first principle is that you must not fool yourself and you are the easiest person to fool."* - Richard Feynman (1918- 1988)
