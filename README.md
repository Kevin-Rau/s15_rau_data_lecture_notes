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

###Lecture 2/5/15

Demonstration 
  - Angular runs in the browser - Node runs the platform - express is a framework that runs on top of node. 
  - Node is middleware based, rails is basically middleware as well. 
   
###Lecture 10-12
  - Demonstration
  
###Lecture 2/17/15
  
Using the twitter_framwork files on Github
  - TwitterRequest 
    - Standardized constructor
    - params that go on request
    - data that is needed by the request
  - The Contract
    - Subclasses may provide implementations of:
      - error: method that handles failed requests
  - Logging
      - Creates a logger, if nothing makes a default logger. 
  - Rates
    - && variable is a class variable in Ruby
  - MaxIdRequest 
    - Traversing the timeline
  
###Lecture 2/19/15

NoSql
  - Web Analytics
    - lets lost of requests come in then batch to the database
    - but once again there are too many requests to handle, can try and add more workers to the the queue
    - still can be inefficeint because they all bottleneck on a one database
    - can solve with vertical scaling, but takes money. 
    - in vertical scaling you can also put a cache before the database to save accessed variables
    - can also SHARED the database - have multiple copies of the database - partition across the database
    - problems are is this is an application level concern, have to manage the number of shards
    - if you make a mistake with the sharding then you have to fix it, if one thing goes down it all goes down
    - humans are the final problem
    - not a crashing bug, just a bug that writes the wrong data in some way
  - NoSql
    - NoSql databases are aware of their distributed nature
    - horizontally scalable
    - does the sharding for you
    - tends to avoid mutable databases
    - cant lose correct data because once it is written it is immutable and cant be updated
    - option to go back in time and get an old value
    - the databases are fault tolerant 
    - relation database is row-stored - if you need to change multiple columns, one row is stored in same place
  - Key-Value - simple database that when presented with a key is returns an abritrarily large set of data
    - act like hash tables
    - values are untyped, can store any type of data in these databases
    - its simple! examples: Amazon SimpleDB, Redis, Voldemort, Riak
  - Graph Stores
    - databases that are optimized to store graoh structues rather can table/row/column structues
    - have structural query languages so you can locate information bases on the stucture of your data
    - have ability to traverse the graph efficently
    - have ability to fine the shortest path between two nodes
    - ex. find pairs of Person nodes who have at least three children, live in colorado, married more than 15 years
    - Neo4j, Titan
  - Columnar Stores
    - Aka Column Family Stores
    - Can scale enormous amounts of data
    - can achieve very fast writes (milliseconds) .. while also keeing reasonable read performance
    - Column Family - think of as a table of related data
    - Column familes consist of rows that have unique row keys
    - Rows consist of columns
    - Columns consist of a key and a value
    - hash tables all the way down
    - Ex. Cassandra, HBase
  - Document Stores
    - key-value store but with more structure
    - you insert documents
    - each document gets indexed in a variety of ways
    - documents can be found via queries on any attribute
    - Documents grouped into collections, collections into databases
    - each database is then used by a partiular application to get its work done
    - Ex. MongoDB, CouchDB, Solr/Lucene
 - Why NoSql?
  - no scheme
  - no types, you can store whatever you want
  
###Lecture 2/24/15

CouchDB
  - What is it 
    - Stores documents 
    - Self-contained data
  - Cap Theorem
    - There are problems when desinging a database when you have one or more server running
    - Issues are, consitency, availability, partition tolerance
    - Cap therom states. pick any two
  - Choices
    - Consistency and Availability - relational databases - low partition tolerance
    - Availability and Partition Tolerance - ability to scale horiz and always be available for requests, but only gurantee eventual consistency 
    - Consistency an Partition Tolerance - consistency across multiple databases, but not always be available for client requests 
  - Where the magic happens
    - Couch makes use of B-Tree storage engine
      - automatic sorting: allow searches, insertions, and deletions to occur in logarithmis time
    - Employs MapReduce over this B-tree to compute views of data, allowing for parallel and incremental computation
    - No Locking
      - Runs under the assumption that there are lots of copies of the database
      - can go in and change documents as much as you wont and not lock them across servers
      - returns a document that was the latest when the read started
      - new version of the document can be written while a read occurs; the next read will return the new document.
    - Validation: Can be written in Javascript for a particular class of document
     - can choose or deny an update to the document when it is submitted, to ensure no bad data is inserted 
     - Merge Conflicts
      - These can happen
      - brew install couchdb
    - Crud opperations are supported
    - Updataing a document
      - When working with a document, use this worlfow
        - Read the entire document
          - provides you with the rev_id
        - Change it
        - Store the updated document

###Lecture 2/26/15

MongoDB
  - History - mid 2007 10gen began working on (PaaS) users wanted their database tech.
  - many companies use MongoDB, written in C++, no fixed schema
  - is a document-based database 
  - documents is a set of keys and values
  - implemented as B-Trees
  - No multi-document atomic transactions are supported
  - Document is the most basic element in mongo, equivalent to a row in a relational database 
  - Cannot have duplicate tags
  - When to use:
    - Makes sense for medical records, some patients can have lost of data
    - read heavey enviorments
  
###Lecture 3/5/15

MongoDB Continued
  - Importing tweets
    - input file is JSON objects
    - Name of database: data
    - name of collection: tweets
    - use mongo Rub gem for accessing MongoDB
  - Connecting to Mongo
    - Include Mongo - import mongo module
    - mongo = MongoClient.new - Connection to mongoDB
    - db = mongo.db('data') = get a handle to the database
    - tweets = db['tweets'] get a handler to the tweets
    - one more thing
  - Running MongoBD
    - mongod --config /usr/local/etc/mongod.conf
    - to launch mongo client just type in 'mongo'

###Lecture 3/31/15

Presntations
  - Grpahing presentation on Neo4J
    - uses nodes and edges
    - Consistency
    - ACID compliant
  
###Lecture 4/2/15

Presentations 
  - Riak
  - Cassandra 
  
