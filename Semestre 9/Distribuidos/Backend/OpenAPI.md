Well use Swagger to follow OpenAPI rules.

we install pip3 install flasgger

export MONGODB_USER=admin
export MONGODB_PASS=pass123
export MONGO_HOST=localhost

localhost:5000/apidocs

we could have methods we dont want to document. 
Swagger allows us to document our API automatically

___
**Deployment**:

on the routes well create a new endpoint `/healthcheck`
curl localhost:5000/healthcheck    -> indicates the docker is UP

- Now we create the Dockerfile

well use gunicorn

one we have our docker-compose:
`docker compose up -d`
`docker compose down`: we remove the docker compose