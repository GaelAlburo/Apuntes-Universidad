In essence a container doesnt persist.
Two types of volumes (storage in docker):
- bindmount
- tmpfsmount
we use storage when we have to use config files, persist the logs of the container.
ELK: an external unit that continouslly extracts all the logs from a container. Then we dont have to use a volume to store the logs

-------
We delte the nginx container
we start it again with the ports
curl localhost -> it doesnt show the changes done in previous session

-------------
TO create a volume: docker volume create <name>
TO list all the volumes: docker volume ls
TO make a container use a certain volume:
	docker run -d --name nginx -p 80:80 -v volume_nginx:/usr/share/nginx/html nginx:latest
	
-v volume_nginx/usr/share/nginx/html : tell what volume we're going to use and in what directory were going to save the container
- to delete a volume: docker volume rm nginx_volume
=========
we create a directory: mkdir /tmp/nginx_data
we create an index: echo 'hello world'> /tmp/nginx_data/index.html
we the create a new container but with the new file added
docker run -d --name nginx -p 80:80 --mount type=bind,src="/tmp/nginx_data",target=/usr/share/nginx nginx:latest
	wITH THIS command we tell it to map the src path (the one we just created locally) to the target path(inside the container). We tell it to be type bind too