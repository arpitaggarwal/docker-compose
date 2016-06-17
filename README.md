### docker-compose

Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a Compose file to configure your application’s services. Then, using a single command, you create and start all the services from your configuration.

# Docker Compose Installation

**Step 1:** Run command - ``` curl -L https://github.com/docker/compose/releases/download/1.7.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose ```

**Step 2:** Apply executable permissions to the binary - ``` chmod +x /usr/local/bin/docker-compose```

**Step 3:** Test docker-compose installation -  ``` docker-compose --version ```

**Step 4:** Create `docker-compose.yml` and run command `docker-compose up`

Reference:
1. https://docs.docker.com/compose/install/
2. https://docs.docker.com/compose/compose-file/


# Some useful docker-compose commands

1. Start up your application - ```docker-compose up ```

2. Run your services in the background - ```docker-compose up -d ```

3. See environment variables available to the service - ``` docker-compose run web env ```

4. Stop up your application -  ```docker-compose stop```

5. Login to Docker container using docker compose `docker-compose run <service-name>`

Reference : https://docs.docker.com/v1.5/compose/cli/


# Docker Machine

1. Install and run Docker on Mac or Windows

2. Provision and manage multiple remote Docker hosts

3. Provision Swarm clusters

Reference: https://docs.docker.com/machine/overview/


# What’s the difference between Docker Engine and Docker Machine?

When people say “Docker” they typically mean Docker Engine, the client-server application made up of the Docker daemon, a REST API that specifies interfaces for interacting with the daemon, and a command line interface (CLI) client that talks to the daemon (through the REST API wrapper). Docker Engine accepts docker commands from the CLI, such as docker run <image>, docker ps to list running containers, docker images to list images, and so on.


Docker Machine is a tool for provisioning and managing your Dockerized hosts (hosts with Docker Engine on them). Typically, you install Docker Machine on your local system. Docker Machine has its own command line client docker-machine and the Docker Engine client, docker.


# Some useful Docker Commands
1. docker stop container

```
docker stop <container-id>
```

2. Stop all containers
```
docker stop $(docker ps -a -q)
```

3. Delete all containers

```
docker rm $(docker ps -a -q)
```

4. Delete all images
```
docker rmi $(docker images -q)
```

5. Login docker container

```
docker exec -i -t <container-id> /bin/bash
```

6. Docker run image

```
docker run -p 8080:8080 --cap-add SYS_PTRACE -it <image-name> /bin/bash
```
