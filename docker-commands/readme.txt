1. **docker run** - Run a command in a new container:
Example: **`docker run -it ubuntu:20.04 bash`**
    - This command starts a new container based on the **`ubuntu:20.04`** image and runs the **`bash`** shell interactively (**`it`**).
2. **docker build** - Build an image from a Dockerfile:
Example: **`docker build -t myapp .`**
    - This command builds a Docker image tagged as **`myapp`** using the Dockerfile located in the current directory (**`.`**).
3. **docker pull** - Pull an image or a repository from a registry:
Example: **`docker pull nginx:latest`**
    - This command pulls the latest version of the **`nginx`** image from Docker Hub.
4. **docker push** - Push an image or a repository to a registry:
Example: **`docker push myusername/myapp`**
    - This command pushes the **`myapp`** image to a Docker registry under the **`myusername`** account.
5. **docker ps** - List running containers:
Example: **`docker ps`**
    - This command lists all running Docker containers along with their IDs, names, status, and other details.
6. **docker images** - List images:
Example: **`docker images`**
    - This command lists all Docker images available on the host system, along with their repository, tag, image ID, and size.
7. **docker exec** - Run a command in a running container:
Example: **`docker exec -it mycontainer sh`**
    - This command runs the **`sh`** shell interactively (**`it`**) inside the **`mycontainer`** container.
8. **docker stop** - Stop one or more running containers:
Example: **`docker stop mycontainer`**
    - This command stops the **`mycontainer`** container gracefully.
9. **docker rm** - Remove one or more containers:
Example: **`docker rm mycontainer`**
    - This command removes the **`mycontainer`** container from the host system.
10. **docker rmi** - Remove one or more images:
Example: **`docker rmi myimage`**
    - This command removes the **`myimage`** Docker image from the host system.
11. **docker-compose up** - Create and start containers defined in the **`docker-compose.yml`** file:
Example: **`docker-compose up -d`**
    - This command creates and starts containers defined in the **`docker-compose.yml`** file in detached mode (**`d`**).
12. **docker-compose down** - Stop and remove containers, networks, and volumes defined in the **`docker-compose.yml`** file:
Example: **`docker-compose down`**
    - This command stops and removes containers, networks, and volumes defined in the **`docker-compose.yml`** file.
13. docker-compose debugging - Run **`docker-compose config`** to see the full configuration that is being interpreted by Docker Compose, which can help you spot any errors or unexpected configurat
    
    Example: **`docker-compose --verbose up`**