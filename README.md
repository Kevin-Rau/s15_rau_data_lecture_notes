# s15_rau_data_lecture_notes
##Class Website: https://github.com/cu-data-engineering-s15/syllabus/wiki

###Lecture Notes for Data Engineering Spring 2015

###Lecture 1/12/15

Prof. Anderson is asking us to create a new repo on GitHub and take notes in Markdown. 

"Big Data" - Social Networks & Data Analytics & Storage
  - sampling - statistics built on sampling, take a sample from city, say 20% here graduate, not exact number 
  - machine learning 
  - Storage -> NoSql - unstructured data, give quieres you want to the best of ability
    - Data Modeling is "wicked hard"
    - Document Databases
    - Graph Databases
    - Key-Value Stores
    - Colomnar 
  - Date Collection & Cleaning
  - Infoviz 
    - D3 - javascript to make visualizations of data 
    - R 
Data Lifecycle
  - Question -> Collection -> Generation -> Clean-up -> Storage -> Processing/Analysis -> Query/Visualization --
  - Curation/Triage - How long data will be around, Triage is prioratizing of a situation,  
Http/Html
  - http request - Request -> Response -> Recycle 

###Lecture 1/15/15

Presentation on Markdown
  - Plain Text formatting
  - Easily converted to HTML
  - Plain text -> rich text
  - Standard Markdown - own type of syntax
  - Github Flavored Markdown
  - bold ** or __
  - italics * or _
  - code block ``` text ```
  - new line is just three underscores, hyphens, or astericks 
   
Web Servers
  - Web Browser -> Web Server/API Server
  - GET/POST/DELETE/PUT
  - When clicking on a page, loads and renders, loads a cookie and knows who I am, sends adds and suggested services
  - Uploads of prodcuts or likes are calls to Web Servies handled in JSON or XML, 
  - Rest is an architecture, reasources all over the world, can ask for those and get that information as a representation
  - Resources are refereced by URI's can ask for one, update, delete it , create a new one
  - 'CRUDE' - Create, Read, Update, Destroy
  - The web is almost a pure representation of REST
  - /users |GET -> READ | POST -> CREATE | PUT -> UPDATE | DELETE -> DESTROY |  
  - get /users - information on all users
  - get users/id - information on particular user
  - 
 
###Lecture 1/20/15 

REST
 - Invented by Roy Fielding 
 - Architectual style for web services
 - Approach to developing web services that mimics the web itself
 - Service provides access to a linked set of resources
 - For each resources you can perform operations on it similar to the mainoperations (methods) of the HTTP specification
 - Rest Operations, for each resource you can typically perform CRUD operations

Discussion
  - Each operation may produce a result
    - With RESTful services, JSON format is king (Java Script Object Notation) 
  - POST and Put methods typically send data
    - Maybe in  URL or in the body of the HTTP Request
    - May be in the URL or the body of the HTTP request in the JSON format.
      - For GET, data may appear as query params
  - Other forms are possible:HTML and XML are typical
  - If a request needs to be authenticated
    - the authenication data appears in HTTP headers

Discussion 2
  - How are operations handles on two resources?
    - /users/0 and /possessions/1 or /2 or /3 ....ect
    - /users/0/possessions - operations on two resources
    - "create new comment on post zero" POST /api/1.0/posts/0/comments 
    - another approach is to perfrom an operaton on one resource, you can reference the other one by id in the data that is sent with that request

Issues
  - Security: How do you authenticate users?
  - Identity: How are ids assigned to resources
  - Failure: How do we handle failure interuptions
    - in example this lecture it is handled in JSON
    - could have used HTTP status codes (404, 500, ect) like GET user 20, respond with Status Codes if not there
    - Most services are handled with both 
  - Persistance: How are resources stored? 

Example
  - Contacts Web Service
  - Implemented in both Ruby and Javascript
  - Tehcn used
    - Sinatra
    - Rspec
    - Typoeus
    - Node
    - Express

###Lecture 1/27/15

Node.JS
  - http provides a function called createServer()
  - It takes a function that implements the servers behavior 
  - createServer() returns an object with a method listen()
    - it accepts the servers network behavior
  -Example(Demo in class) 
  
###Lecture 2/2/15
  - Angular.js 
    - is a client -side web application framework written in javascricpt for use in most web servers
    - has implementation of model view controller in the web browser to make it easier to make modular web clients
    - not the easiest learning curve
    - but very powerful!
    - just learn its core concepts and idioms - learning version 1.3
    - Core concepts
      - Data bindings
      - value of an HTML tag can be associated with a model object. When ones changes, Angular updates other autom
      - Controllers
      - Controllers are associated with portion of your HTML and define all states and methods that can be acessed in that page
      - With controllers can modularize page
      - Services
      - controllers are used to manage data for some portion of a page while it is displayed. as you move from mage to page they will come and go out of existing 
      - can make a service to keep the state of controllers
      - Directives - umbiquitous in Angular; primary use is to allow Angular to intergrate in HTML in natural way
      - Also can be used to create reusable componentes that combine controllers, data and Html
      - Embeddable - Angular can control as little or as much of a webpage as you specify
      - Injectable - "dependancy injection" - declare independancies upfront
      - Modules - is primary way to package up a set of controllers in Angular
      - can create a module with no dependancies, and handle on it
      - once you have a mod defined in javascript, can tell angular where is lives
      - to actullay do something in angular you need to create a module
    - Demonstration 

