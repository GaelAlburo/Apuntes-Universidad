Its a microframework.
A framework gives certain tools to facilitate the work.

Flask facilitates the development of web apps. But it doesnt contain libraries or tools, thats why its called a microframework

Doesnt limits us.

Flask is based on:
- Werkzeug - library to manage HTTP requests
- Jinja2 - Templates

In Python we use a virtual environment (venv) so we can install dependencies and not affect the system (in linux every package installer uses python).

# Install Flask

We'll make virtual environment. Theyre isolated places where we can install

we create a venv

We upgrade pip: `pip3 install --upgrade pip`

pip3 list

pip3 install Flask
- Flask version 2 and 3 are very different. We use 3

When we create the app.py. We must select the interpreter of our venv. We select python3.12

`__name__`: references the name of the file

## Routes, Views and Templates:

Every route is associated with a function that will always return something.

Views:  Theyre functions that are going to execute when accesing a route.


# HTTP Requests

Client --- Request --> Server
Client <-- Response -- Server

- GET - Retreive data from server - READ
- POST - Send data to server to create a new resource - CREATE
- PUT - Update an existing resource on server - FULL UPDATE
- PATCH - Partially update a resource - PARTIALLY UPDATE
- DELETE - Delete an existing resource on server - DELETE
	- Soft delete - place a flag on a register and mark it as disabled, but not actually delete it from system
	- Hard delete - completely delete from system


## HTTP Codes

1XX 
- 100  Continue - The client must continue the request
- 101  Switching Protocols - The server accepts the switch of communication protocol

2XX
- 200 OK - Successful request - GET, PUT, DELETE
- 201 Created - Resource created successfully - POST, PUT
- 204 No Content - Successful operation with no content - DELETE

>[!info] By default it'll always return a 200 OK Code

3XX
- 301 Moved Permanently - The resource has been permanently moved to a new URL
- 302 Found - The resource is temporarily located at a new location
- 304 Not Modified - The resource has not changed since the last request

4XX
- 400 Bad Request - Bad request or invalid data
- 401 Unauthorized - The client is not authenticated
- 403 Forbidden - The client does not have permissions for the resource
- 404 Not Found - The requested resource does not exist

> [!info] 404 request is a signal for security. People can search what resources exists. If we have various 404 requests, we can know there is a security vulnerability

5XX
- 500 Internal Server Error - The server encountered an unexpected error
- 503 Service Unavailable - The server is temporarily unavailable

sonarcube