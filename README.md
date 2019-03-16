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

I found a nice basic blue navigation bar design on a free artist website.  I downloaded the scripts and tried them out.  First attempt did not quite work the way I had hoped, but did not give up on trying to figure out what was needed for the project.  Eventually, I was able to get all of the source files that the artist used for the navigation bar and found a JQuery reference and that javascript file was referenced inside the HTML Body tag to be able to run in the background during a page load.

    <nav class="nav">
        <ul>
            <li><a href="#">Home</a>
            <li><a href="#">Forum</a>
            <li class="drop">
                <a href="#">User</a>
                <ul class="dropdown">
                    <li><a href="#">Profile</a></li>
                    <li><a href="#">Settings</a></li>
                    <li><a href="#">Maybe Something Else</a></li>
                </ul>
            </li>
            <li><a href="#">Register</a>
            <li><a href="#">About</a>
        </ul>
        <!--  JQuery and JS Runtime Include -->
        <!-- These two script tags fir the JQuery librsry snd the Navbar.js were placed here so that they
        will populate into the body section of a web page that references this navbar.html inclusion.
        It is necessary to make the rollover functionality behave during runtime.
        -->
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
        <script src="/static/js/navbar.js"></script>
        <!--  END JQuery and JS Runtime Include -->
    </nav>

To quickly deploy the navigation bar to all the sites, it was incorporated into the Base.HTML source file that is extended off to create all the other web site pages in the application.

     {% load static from staticfiles %}
      <html lang="en">
     <head>
         <meta charset="UTF-8">
         <title>{% block title %}{% endblock %}</title>
         <meta name="viewport" content="width=device-width, initial-scale=1">
         <link rel="stylesheet" type="text/css" href="{% static 'css/layout.css' %}">
         <link rel="stylesheet" type="text/css" href="{% static 'css/navbar.css' %}">
         <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
     </head>
     <body>
         <main>
             {% include "partials/navbar.html" %}
             <div class="forum-container">
                 <header class="header-title">
                     <h1>{% block header %}{% endblock %}</h1>
                 </header>
                 {% block content %}{% endblock %}
             </div>
         </main>
     </body>
     </html> 

## Other Skills Learned

* Fundamental runtime troubleshooting of a Python and Django environment.  Some basic issues I encountered were when to use the static director alias, or the static url alias in the application settings file.
* Deconstructing someone else's HTML and CSS design work to find elements and items that I like and incorporate them into my build work.
* First time using Azure DevOps on a cloud platform, I have typically done most of my work with TFS on-prem code repositories.