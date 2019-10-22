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

  create_router.js

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?

  public and src are still in client but a server directory has been created to save server.js and helpers/create_router.js for server operations. This allows them to be seperate and for different NPMs to be run.

3. What are the the responsibilities of server.js?

  server.js connects to MongoClient and listens for requests on localhost:3000

4. What are the responsibilities of the `gamesRouter`?

  gamesRouter modularises our routes to avoid repetition

5. What process does the the client (front-end) use to communicate with the server?

  GamesServices uses fetch to communicate with baseURL on 'http://localhost:3000/api/games'

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs

  fetch uses second optional stringify to use json instead of HTML. In this case it allows for a return of json from the database to confirm a game has been added.

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?

  Game routes through create_router which uses router.get, router.post, router.delete and router.put

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?

  we can use the driver to use gpu apps such as compass for data visualisation.

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

  Using ObjectId allows for the copying of _id for entries which can then be used for updating and deleting MongoDB database documents.

Add to your diagram the dataflow for removing a game.
