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

## Guidelines

## Notes

Parameter <container> can be container id or name