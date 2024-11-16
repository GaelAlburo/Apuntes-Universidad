Is a set of rules that define how we can interface with users.

The most known are RESTful.
- They do CRUD
- They communicate with HTTP requests

REST - Representación de estado de transferencia.
Its an architectural style, like MVC, SOA, Microservices, etc

- Every resource in a REST API is an endpoint, an URL.
- The (HTTP) requests to a REST API go to the resources. 
- They're stateless. The API contains all the information necessary to work, it doesn't need to consult any third party
- REST always returns data in JSON (mostly used) or XML
	- If our app understands JSON, it can connect to any REST API

Stateless / Stateful

Stateless: They dont save a state. They dont save things. They can connect to a DB and save things in the DB, but not actually in the API

Stateful: Saves data in the API itself, like cookies

___

For our API well create:
- Logger (for login)
- Models (DB connection)
- Service (Logic)
- Schemas (Validation)
- Routes (URL)
- App.py

first we create the virtual env

- upgrade pip
- pip3 install flask
- pip3 install pymongo

In python, the files will be called in snake case. Because of issues of importing python has
We create a container with mongodb


docker run --name mongodb -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=pass123 -v /opt/mongodb_data:/data/db mongo


create the directory for data storage:
	sudo mkdir /opt/mongodb_data
	id
	sudo chown \<user>/opt/mongodb_data

after we create the directory, we create the container

We download MongoDB Compass, an GUI to interact with our mongo DB
When we create the connection
Inside the connection there will already be 2 DBs

We create  a new DB called microservices, iwth a collection called *books*

Inside it we create a new document:
```json
[
	{
		"_id": 1,
		"title":, "Title 1",
		"author": "Author 1",
		"year": "1991",
		"edition": "First Edition"
	}
	{
		...
	}
]
```

We need to use `_id` because this is how MongoDB uses ids. If we were to add a different name for this id, mongo will create a `_id` of its own

to fix eerror with logger: export PYTHONPATH-$PYTHONPATH

in terminal we set the environtment variables:
export MONGO_DB_USER=admin
export MONGO_DB_PASS=pass123
export MONGO_DB_HOST=localhost
