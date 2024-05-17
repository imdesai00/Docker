- A Docker image is a lightweight, standalone, executable package that contains everything needed to run an application, including the code, runtime, libraries, and dependencies.
- Images are built from Dockerfiles using the **`docker build`** command or pulled from a registry like Docker Hub.
- Images are stored as read-only templates and can be shared, distributed, and reused across different environments.

- **Description**: Docker image is a read-only template used to create containers. It contains the application code, runtime, libraries, and dependencies.
- **Example**: After building a Docker image using a Dockerfile, you can create containers from it.
- **Code**: To create a container from a Docker image, run the following command
    
    ```bash
    docker build . //to create your docker image
    docker run my-node-app
    ```