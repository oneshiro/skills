# Docker — Get Started

Sourced snippets (22 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Clone the sample application repository

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/build-tag-and-publish-an-image.md

Clones the getting-started todo app sample repository to your local machine using Git.

```console
$ git clone https://github.com/docker/getting-started-todo-app
```


--------------------------------

### Clone the sample to-do app repository

Source: https://github.com/docker/docs/blob/main/content/get-started/tutorials/run-an-app.md

Clones the getting-started-todo-app repository from GitHub and changes into the project directory.

```console
$ git clone https://github.com/docker/getting-started-todo-app
$ cd getting-started-todo-app
```


--------------------------------

### Build and tag a Docker image with example username

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/build-tag-and-publish-an-image.md

Example build command demonstrating tagging the image with the specific username mobywhale.

```console
$ docker build -t mobywhale/concepts-build-image-demo .
```


--------------------------------

### Start container with docker run

Source: https://github.com/docker/docs/blob/main/content/get-started/tutorials/run-an-app.md

Runs the container in the background, assigns the name welcome, and maps host port 8080 to container port 80.

```console
$ docker run --detach --name welcome --publish 8080:80 docker/welcome-to-docker
```


--------------------------------

### Start application with Docker Compose

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/running-containers/multi-container-applications.md

Run docker compose up with the -d and --build flags from the project directory to build images and start services defined in compose.yml in the background.

```console
$ docker compose up -d --build
```

```console
 ✔ Network nginx-node-redis_default   Created                                                                                                   0.0s
 ✔ Container nginx-node-redis-web2-1  Created                                                                                                   0.1s
 ✔ Container nginx-node-redis-web1-1  Created                                                                                                   0.1s
 ✔ Container nginx-node-redis-redis-1 Created                                                                                                   0.1s
 ✔ Container nginx-node-redis-nginx-1 Created   
 
```


--------------------------------

### Install production dependencies using RUN

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/writing-a-dockerfile.md

Executes yarn install to install production application dependencies inside the container.

```dockerfile
RUN yarn install --production
```


--------------------------------

### Start the application with docker compose up

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/the-basics/what-is-docker-compose.md

Builds and starts the services in detached mode, provisioning images, application networks, volumes, and running containers.

```console
docker compose up -d --build

```

```console
[+] Running 5/5
✔ app 3 layers [⣿⣿⣿]      0B/0B            Pulled          7.1s
  ✔ e6f4e57cc59e Download complete                          0.9s
  ✔ df998480d81d Download complete                          1.0s
  ✔ 31e174fedd23 Download complete                          2.5s
  ✔ 43c47a581c29 Download complete                          2.0s
[+] Running 4/4
  ⠸ Network todo-list-app_default           Created         0.3s
  ⠸ Volume "todo-list-app_todo-mysql-data"  Created         0.3s
  ✔ Container todo-list-app-app-1           Started         0.3s
  ✔ Container todo-list-app-mysql-1         Started         0.3s

```


--------------------------------

### Start interactive container from node-base image

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/understanding-image-layers.md

Starts an interactive container named app-container using the node-base image.

```console
$ docker run --name=app-container -ti node-base
```


--------------------------------

### Start multi-container stack with docker compose up

Source: https://github.com/docker/docs/blob/main/content/get-started/tutorials/run-an-app.md

Reads compose.yaml, builds required service images with --build, and starts the full service stack in the background with --detach.

```console
$ docker compose up --build --detach
```


--------------------------------

### Start an interactive Ubuntu container

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/understanding-image-layers.md

Starts a new interactive container named base-container from the Ubuntu base image and opens a shell prompt inside it.

```console
$ docker run --name=base-container -ti ubuntu
```

```console
root@d8c5ca119fcd:/#
```


--------------------------------

### Clone the sample repository

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/the-basics/what-is-docker-compose.md

Clones the sample to-do list multi-container application from GitHub.

```console
git clone https://github.com/dockersamples/todo-list-app 

```


--------------------------------

### Validate Node.js installation

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/understanding-image-layers.md

Runs an inline JavaScript command inside the container shell to verify Node.js is installed correctly.

```console
$ node -e 'console.log("Hello world!")'
```


--------------------------------

### Start first web container with docker run

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/running-containers/multi-container-applications.md

Runs the first web application backend container configured with hostname and network alias web1.

```console
$ docker run -d --name web1 -h web1 --network sample-app --network-alias web1 web
```


--------------------------------

### Run container from sample-app image

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/understanding-image-layers.md

Runs a new container using the sample-app image, executing its default command automatically.

```console
$ docker run sample-app
```


--------------------------------

### Start Postgres container with named volume

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/running-containers/persisting-container-data.md

Starts a Postgres container in the background, sets a password, and attaches the postgres_data volume to /var/lib/postgresql.

```console
$ docker run --name=db -e POSTGRES_PASSWORD=secret -d -v postgres_data:/var/lib/postgresql postgres:18
```


--------------------------------

### Clone repository and navigate to sample directory

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/running-containers/multi-container-applications.md

Clones the nginx-node-redis sample application repository from GitHub and changes into the project root directory.

```console
$ git clone https://github.com/dockersamples/nginx-node-redis
```

```console
$ cd nginx-node-redis
```


--------------------------------

### Start httpd container in background

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/running-containers/sharing-local-files.md

Starts the httpd service in detached mode and publishes port 8080 on the host to port 80 in the container.

```console
$ docker run -d -p 8080:80 --name my_site httpd:2.4
```


--------------------------------

### Sign in to Docker with sbx

Source: https://github.com/docker/docs/blob/main/content/get-started/tutorials/run-an-agent.md

Authenticates the Docker Sandboxes CLI after installation.

```console
$ sbx login
```


--------------------------------

### Install Node.js inside the container

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/understanding-image-layers.md

Updates apt package lists and installs Node.js directly within the container's writable filesystem layer.

```console
$ apt update && apt install -y nodejs
```


--------------------------------

### Navigate to downloaded sample repository directory

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/running-containers/multi-container-applications.md

Changes directory into the extracted archive directory when downloading the sample application source instead of cloning via Git.

```console
$ cd nginx-node-redis-main
```


--------------------------------

### Build the Docker image initially

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/building-images/using-the-build-cache.md

Executes the initial build for the Docker image. The first build takes longer because dependencies must be installed from scratch.

```console
$ docker build .
```

```console
[+] Building 20.0s (10/10) FINISHED
```


--------------------------------

### Navigate to the project directory

Source: https://github.com/docker/docs/blob/main/content/get-started/docker-concepts/the-basics/what-is-docker-compose.md

Changes directory into the cloned repository containing the compose.yaml configuration file.

```console
cd todo-list-app

```
