#docker #networking

## Networking

- Container to ==WWW==
		- no additional configuration required
- Container to ==Host Machine==
		- in the code, instead of localhost use **`host.docker.internal`**. Docker will convert that into ip of hostmachine as seen from inside the container.
		- *e.g: can use `mongodb://host.docker.internal:<port>/<api endpoint>` to communicate with database installed in host machine* 
- Container to ==Container==
		- Basic way: find the **IP address** of the other container and use it in the code to communicate.
		- elegantway: use **`docker network create <network name>`** to create a network. when running container use `--network <network name>` to attach container to this network.
		- instead of localhost, conainers of same network can connect to eachother using container names.
		- *e.g: can use `mongodb://mongodb-container:<port>/<api endpoint>` to communicate with database in mongodb-container* 