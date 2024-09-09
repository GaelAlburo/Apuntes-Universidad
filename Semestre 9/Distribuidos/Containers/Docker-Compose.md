Its a tool that allows us to define and execute apps on docker
We do the define on YML files
With these YML files we can orchestrate multiple containers on one single command
	docker-compose: legacy com
We create the file docker-compose.yml
	On YML tabs are important, like Python
A service is an app that we cant to place on a container
Restart tells the container what to do if it dies
To pass an env variable though CLI: docker run -e "VARIABLE=value"
	env variables modifies user session
	they only exist on the current session of SSH
		to make them last we place them on .bashre or .profile
		/etc/profile -> SYstem
YML Program:
services:
  db:(we do 2 spaces, not a tab)
    image: mariadb:11.4.2(2 spaces again)
    restart: always
    environment:
      MARIADB_ROOT_PASSWORD: password123 (we change the env variable value for password)
    volumes:
      - mariadb_data:/var/liv/mysql (we create a volume to persist data and a path to save the values)
  adminer:
    image: adminer:4.8.1
    restart: always
    ports:
      - 8080:8080 (host:container)
    depends_on: (tells order of execution of containers)
      - db
volumes: (tells docker to create a volume. IN db service we just reference it)
  mariadb_data: (has to be same name)
  
  
-------
we use docker compose up -d
This creates a network, an internal net on the containers to they comunicate with each other.
we can use docker compose ps. this gives us all the containers inside the docker compose
To delete the containers: docker compose down
And also the network.
But the images and the volumes doesnt. we have to delete them manually

-----
Scan containers and check for vulnerabilities in them:
dockle
trivy
OWASP | MITTRE - standards these two tools use