# Docker-Commands

## Getting Started With Docker

| CLI Commands                     | Description                                     |
| :------------------------------- | :---------------------------------------------- |
| `docker run -d -p 80:80 docker/getting-started`  | Create and run a container in the background. `-d`: Detached mode, `-p 80:80`: Map port 80 to port 80 in the container, `docker/getting-started`: The image to use. |
| `docker run -it -p 8001:8080 --name my-nginx nginx` | Create and run a container in the foreground. `-it`: Interactive bash mode, `-p 8001:8080`: Map port 8001 to port 8080 in the container, `--name my-nginx`: Specify a name, `nginx`: The image to use. |

## General Commands

| Cli Commands        | Description                                                                                   |
| :----------------- | :-------------------------------------------------------------------------------------------- |
| docker ps        | List running containers                                           |
| docker ps -a        | List all containers                                            |
| docker ps -s | List running containers (with CPU / memory)      |
| docker images            | List all images          |
| docker exec -it <container> bash      |  Connecting to container |
| docker logs <container>             | Shows container's console log |
| docker stop <container>            | Stop a container |
| docker restart <container>	              | Restart a container |
| docker rm <container>	       | Remove a container|
| docker port <container>         | Shows container's port mapping |
| docker top <container>          | List processes|
| docker kill <container>          | Kill a container|

## Docker Containers

### Starting & Stopping

| CLI Commands                     | Description                            |
| :------------------------------- | :------------------------------------- |
| `docker start my-nginx`           | Starting a container                   |
| `docker stop my-nginx`            | Stopping a container                   |
| `docker restart my-nginx`         | Restarting a container                 |
| `docker pause my-nginx`           | Pausing a container                    |
| `docker unpause my-nginx`         | Unpausing a container                  |
| `docker wait my-nginx`            | Blocking a container                   |
| `docker kill my-nginx`            | Sending a SIGKILL to a container       |
| `docker attach my-nginx`          | Connecting to an existing container    |

## Container Information

| CLI Commands                     | Description                                     |
| :------------------------------- | :---------------------------------------------- |
| `docker ps`                       | List running containers                         |
| `docker ps -a`                    | List all containers                             |
| `docker logs my-nginx`            | Container logs                                  |
| `docker inspect my-nginx`         | Inspecting containers                           |
| `docker events my-nginx`          | Container events                                |
| `docker port my-nginx`            | Public ports                                    |
| `docker top my-nginx`             | Running processes                               |
| `docker stats my-nginx`           | Container resource usage                        |
| `docker diff my-nginx`            | Lists the changes made to a container           |

## Creating Docker Image

| Option                             | Description                                 |
| :--------------------------------- | :------------------------------------------ |
| `-a, --attach`                     | Attach stdout/err                           |
| `-i, --interactive`                | Attach stdin (interactive)                  |
| `-t, --tty`                        | Pseudo-TTY                                  |
| `--name NAME`                      | Name your container                         |
| `-p, --publish 5000:5000`          | Port map (host:container)                   |
| `--expose 5432`                    | Expose a port to containers                 |
| `-P, --publish-all`                | Publish all ports                           |
| `--link container:alias`           | Linking containers                          |
| `-v, --volume \`pwd\`:/app`        | Mount (absolute paths needed)               |
| `-e, --env NAME=hello`             | Environment variables                       |

## Docker Container Creation

```bash
docker create [options] IMAGE
```

## Docker Create Command

| Command                                          | Description                                                                                                                                                        |
| :----------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `docker create --name my_sql --expose 3306 mysql:latest` | Create a new Docker container named `my_sql` from the latest MySQL image. The command also exposes port `3306` for internal communication with other Docker containers in the same network. The container is not started immediately, allowing for further configuration if needed. |

### Example

```bash
docker create --name my_sql --expose 3306 mysql:latest
```

## Managing Containers

| Command                                                 | Description                                                                                       |
| :------------------------------------------------------ | :------------------------------------------------------------------------------------------------ |
| `docker rename my-nginx my-new-nginx`                   | Rename a container from `my-nginx` to `my-new-nginx`.                                              |
| `docker rm my-nginx`                                    | Remove a container named `my-nginx`.                                                               |
| `docker update --cpu-shares 512 -m 300M my-nginx`       | Update the resource limits of the `my-nginx` container. This sets CPU shares to `512` and memory limit to `300MB`. |

## Docker Images

### Manipulating Images

| Command                                        | Description                                                             |
| :--------------------------------------------- | :---------------------------------------------------------------------- |
| `docker images`                                | List all Docker images available on the system.                         |
| `docker rmi nginx`                             | Remove an image named `nginx` from the system.                          |
| `docker load < ubuntu.tar.gz`                  | Load a tarred repository from a file named `ubuntu.tar.gz`.             |
| `docker load --input ubuntu.tar`               | Load a tarred repository using the `--input` option.                    |
| `docker save busybox > ubuntu.tar`             | Save an image named `busybox` to a tar archive named `ubuntu.tar`.      |
| `docker history nginx`                         | Show the history of the `nginx` image.                                  |
| `docker commit nginx my_nginx_image`           | Save a running container named `nginx` as a new image called `my_nginx_image`. |
| `docker tag nginx eon01/nginx`                 | Tag the `nginx` image with the name `eon01/nginx`.                      |
| `docker push eon01/nginx`                      | Push the `eon01/nginx` image to a remote repository (e.g., Docker Hub). |

## Building Images

### Docker Build

| Command                                                     | Description                                                                                                    |
| :---------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------- |
| `$ docker build .`                                           | Build a Docker image from the Dockerfile in the current directory.                                              |
| `$ docker build github.com/creack/docker-firefox`            | Build a Docker image directly from a GitHub repository.                                                         |
| `$ docker build - < Dockerfile`                              | Build a Docker image using a Dockerfile passed through standard input.                                          |
| `$ docker build - < context.tar.gz`                          | Build a Docker image from a compressed context (e.g., a `.tar.gz` file).                                        |
| `$ docker build -t eon/my-nginx .`                           | Build a Docker image and tag it as `eon/my-nginx`.                                                              |
| `$ docker build -f myOtherDockerfile .`                      | Build a Docker image using a specific Dockerfile named `myOtherDockerfile`.                                     |
| `$ curl example.com/remote/Dockerfile | docker build -f - .` | Download a remote Dockerfile using `curl` and build a Docker image from it using the standard input (`-`).      |

## Docker Networking

### Manipulating Networks

| Command                                                        | Description                                                                                  |
| :------------------------------------------------------------- | :------------------------------------------------------------------------------------------- |
| `docker network rm MyOverlayNetwork`                           | Remove a network named `MyOverlayNetwork`.                                                   |
| `docker network ls`                                            | List all Docker networks available on the system.                                            |
| `docker network inspect MyOverlayNetwork`                      | Get detailed information about a specific network named `MyOverlayNetwork`.                  |
| `docker network connect MyOverlayNetwork nginx`                | Connect a running container named `nginx` to the `MyOverlayNetwork`.                         |
| `docker run -it -d --network=MyOverlayNetwork nginx`           | Start a new container named `nginx` and connect it to the `MyOverlayNetwork` at startup.     |


## Creating Networks

| Command                                                                                               | Description                                                                                                                   |
| :---------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------- |
| `docker network create -d overlay MyOverlayNetwork`                                                   | Create a new network named `MyOverlayNetwork` using the `overlay` driver.                                                     |
| `docker network create -d bridge MyBridgeNetwork`                                                     | Create a new network named `MyBridgeNetwork` using the `bridge` driver.                                                       |
| `docker network create -d overlay \`<br>  `--subnet=192.168.0.0/16`<br>  `--subnet=192.170.0.0/16`<br>  `--gateway=192.168.0.100`<br>  `--gateway=192.170.0.100`<br>  `--ip-range=192.168.1.0/24`<br>  `--aux-address="my-router=192.168.1.5"`<br>  `--aux-address="my-switch=192.168.1.6"`<br>  `--aux-address="my-printer=192.170.1.5"`<br>  `--aux-address="my-nas=192.170.1.6"`<br>  `MyOverlayNetwork` | Create a more complex overlay network named `MyOverlayNetwork` with specific subnets, gateways, IP ranges, and auxiliary addresses.  |

## Clean Up

### Clean All

| Command                              | Description                                                                                                              |
| :----------------------------------- | :----------------------------------------------------------------------------------------------------------------------- |
| `docker system prune`                | Cleans up dangling images, containers, volumes, and networks that are not associated with any containers.                |
| `docker system prune -a`             | Additionally removes any stopped containers and all unused images, not just dangling images.                             |

## Containers

| Command                                         | Description                                       |
| :---------------------------------------------- | :------------------------------------------------ |
| `docker stop $(docker ps -a -q)`                | Stop all running containers.                      |
| `docker container prune`                        | Delete all stopped containers.                    |

## Guidelines

## Notes

Parameter <container> can be container id or name