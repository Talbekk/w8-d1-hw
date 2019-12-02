# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using Vue, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?

The 'gamesRouter' is responsible for defining the routes of the 'games' resource. It creates a router of routes for it while using the gamesCollection information.

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?

The folder structure clearly defines the responsibilities of the client and the server sides of the application.

The client side, or front-end, deals with the vue files that work to create the front-end of the app. It deals with the layout and structure of the form to submit new games and for the list of items that the user can edit and delete as they see fit.

The server side, or back-end, of the app mediates the flow of information to the user. It takes new data from the front-end and creates, updates and deletes the information as requested. It is also responsible for filling the database with any seeds set out beforehand.

3. What are the the responsibilities of server.js?

The server.js contains all of our server code. It has access to Express which allows the server to be installed. It is responsible for configuring the server. Items in the server.js include:

- the body-parser extracts the body from the POST request and makes it accessible.
- the Mongo-client connects the server to the database.
- the cors function allows for our API to be accessible to particular domains and ports.
- the routers are connected to particular data sets and create the RESTful routes to save time and keep code dry.
- the listen method keeps the web server running, waiting for requests from the client so that it can respond quickly.

4. What are the responsibilities of the `gamesRouter`?

The 'gamesRouter' creates a  routes handler that we have created with createRouter. It acts a modular router that can be used again and again. It then passes in the required information from a particular database and generates requests for the API.


5. What process does the the client (front-end) use to communicate with the server?


6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs.

The optional second argument contains an 'init' object that allows you to control a number of different settings. These include the method that you wish to execute, if left blank, this will default to GET. The body includes the data involved in the request. This could be an object. The third item is the header that includes any additional information necessary to the request, such as API keys.

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?

The API routes consumed in the app are GET, POST and delete. You can add new games, see the games list and delete them.

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?

The MongoDB driver allows our app to communicate with our Mongo Database.

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

The object ID is an incredibly unique identifier and because mongo is 'humongous', it allows us to search for a specific entry in a sea of data.

Add to your diagram the dataflow for removing a game.
