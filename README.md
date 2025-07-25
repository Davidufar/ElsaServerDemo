This project demonstrates a simple yet powerful workflow built using Elsa Workflows in ASP.NET Core. The workflow interacts with the Reqres.in mock REST API to fetch user data based on input provided via HTTP.

The application hosts a workflow (GetUser) that listens for an incoming HTTP GET request at /users/{userid}, extracts the userid from the route, sends a request to https://reqres.in/api/users/{userid}, and returns the user data if found, or a 404 Not Found message if not. This makes it a perfect minimal example of using Elsa Workflows, HTTP activities, external API communication, JSON handling, and custom responses based on HTTP status codes.

The core logic lives in two main parts: the Program.cs file which bootstraps and configures Elsa and the web app, and the GetUser.cs workflow file which defines the actual logic of what happens when a request is made.

The Program.cs file sets up Elsa with support for:

Entity Framework Core using SQLite

Elsa workflow runtime and management modules

Identity and admin API key support

JavaScript, C#, and Liquid expressions for dynamic behavior

HTTP and scheduling activities

API exposure for use with tools like Elsa Studio

CORS policies to enable designer communication

The GetUser workflow itself works as follows: it starts when a GET request hits the route /users/{userid}. It reads the userid from the URL, then sends an HTTP GET request to the Reqres API with that ID. If the API returns a 200 OK, the workflow extracts the user information and sends it back in the response. If the user is not found (404), it responds with a “User not found” message.

This project is a good starting point for learning:

How to wire up Elsa in a modern .NET application

How to define HTTP-triggered workflows

How to use Elsa variables and expression syntax

How to handle conditional HTTP responses

How to integrate external APIs into Elsa workflows

Feel free to clone this project and expand it with more workflows, persistence, or UI integrations using Elsa Studio.
