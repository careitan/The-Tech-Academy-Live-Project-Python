# The-Tech-Academy-Live-Project-Python

## Introduction
For the two week time period of 3/4/2019 - 3/15/2019 while at The Tech Academy I worked on a team project with a colelction of other students.  The program was a user forum and message board designed and built with Python.
The project was setup in such a way that it seemed like a starting project.  This would be a situation that I would expect to find as an early career software engineer or developer.  The application had been scoped out and a general frame work in place for the application.  We started with what would be sprint #1 for this team and just got right to work on building features to include on the application.
The ticket(s) that I focused on were the ones that required building the 

## User Stories worked on

* [CSSGRID Layout](#cssgrid-layout)
* [Navigation Bar](#navigation-bar)

### CSSGRID Layout

Many of my peers were used to working with Bootstrap as a basic grid layout tool for HTML paired with CSS.  However, I have had some serious prior background work on teams that built raw CSS layouts for web sites.  This ticket was an opportunity to get back to my roots and try a new idea that I had not perofrmed before with CSS.  The CSS Grid we laid out defined a basic 9 point (3 x 3) grid arrangement area, and added a panel layout for use with the messaging forum.  The panel layout was intended to have one master row at the top for banner / message intro.  Then ten rows of content material attached below it and a bottom footer row for any type of buttons or admin messages.

Here are some samples of my CSSGRID layout pattern:

 html, body
 {
    height: 100%;
    margin: 0;
    padding: 0;
 }

 h1
 {
    color: #080808;
    font-family: 'Arial';
    margin: 0 auto;
 }

 /* The main level container for the Forum */
 .forum-container
 {
    display: grid;
    grid-template-rows: 3fr 10fr 1fr;
    grid-template-columns: 1fr 10fr 1fr;
    grid-template-areas:
        "navbar navbar navbar"
        "lside main rside"
        "footer footer footer";
    grid-gap: .50em;
 }

 /* A panel layout for use inside the forum container */
 .forum-panel
 {
    display: grid;
    grid-template-rows: repeat(12, 1fr); /* 1 row for the top of the message panel. 10 rows in the middle, one row for the bottom.*/
    grid-template-columns: 2fr 10fr 3fr;
 }


### Navigation Bar



## Other Skills Learned
