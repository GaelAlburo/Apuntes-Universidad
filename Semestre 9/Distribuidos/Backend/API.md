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

___


-we left on creating BookModel.
	- it can connect to mongodb
	- it doesn't do any operations

------------------------------------------------

we did:
- Logger
- Model

We must create:
- service
- schema (validations)
- routes
- deploy(app)
- integrate UI

----------------------------------------------
SERVICE

we create bookshelf-back/services/book_services.py

when we have the service code
we execute the service file.

export PYTHONPATH

--------------------------------------------

we wont do the schemas for now, we dont need to validate anything when reading

--------------------------------------------

ROUTES:
bookshelf-back/routes/book_routes.py

well use the method blueprint.
So we can reuse routes, and we can create a route table. We assign a route to a method

blueprint allows us to create a routing table, so we can map the routes, methods and type of request (GET, POST, etc)
With it we can also reutilize this routing table

-----------------------------------------
APP:

bookshelf-back/app.py

we execute the app.py

in another terminal we do: curl -X GET https://localhost:5000/api/v1/books (or http://127.0.0.1:5000/api/v1/books)

--------------------------------------

INTEGRATE UI

well create a soft link: ln -s ~/frontend/examples/bookshelf ./bookshelf-front
	a symbolic link. (a direct access in Windows). 

when we execute the command we do it inside /backend/examples
well get a reference to the whole frontend project inside our backend directory


we have to install axios: (axios allows us to do calls to the API)
	npm install axios (inside backend/examples/bookshelf-front)


FRONTEND:
Inside our app/page.jsx
Well also import useEffect alongside useState

import axios from "axios";


- on line 15, well change the field 'id' to '_id'

- on line 69, const [rows, setRows] = useState(initialRows) change to: useState()

- we delete the whole constants folder

- we also delete the initialRows import

- after const [alert, setAlert]:

useEffect(() => {
	fetchBooks();
}, [])

const fetchBooks = async () => {
  try{
    const response = await axios.get("https://localhost:5000/api/v1/books") # when we containerize, we dont use localhost, we must place the service name and the port
    setRows(response.data)
  }
  catch (error) {
    console.error("Error fetching books:", error);
    setAlert({message: 'Failed to load books', severity: 'error'})
    setOpenAlert(true);
  }
}




CORS is a security. We must define who can and cant access to our API. If we dont configure it we wont see anything in front

- in out venv we install (back): pip3 install flask-cors

in our app.py: we set who has permission to our API with CORS(app)



Bakc to FRONT:
In our DataGrid we place:
	getRowId={(row) => row._id}





------------------------------------------------------------------------------------
CREATE 

1. we modify the service
