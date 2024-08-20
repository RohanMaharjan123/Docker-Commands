# Docker-Commands

## Getting Started With Docker

## General Commands

| CLI Commands                     | Description                                     |
| :------------------------------- | :---------------------------------------------- |
| `docker run -d -p 80:80 docker/getting-started`  | Create and run a container in the background. `-d`: Detached mode, `-p 80:80`: Map port 80 to port 80 in the container, `docker/getting-started`: The image to use. |
| `docker run -it -p 8001:8080 --name my-nginx nginx` | Create and run a container in the foreground. `-it`: Interactive bash mode, `-p 8001:8080`: Map port 8001 to port 8080 in the container, `--name my-nginx`: Specify a name, `nginx`: The image to use. |

## General commands

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

## 


## Guidelines 

## Notes

Parameter <container> can be container id or name