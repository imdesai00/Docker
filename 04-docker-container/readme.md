- A Docker container is a runnable instance of a Docker image. It encapsulates an application and its dependencies in an isolated environment.
- Containers run as lightweight processes on the host system, sharing the kernel with other containers but isolated in terms of filesystem, networking, and resources.
- Containers can be started, stopped, paused, deleted, and managed using Docker commands like **`docker run`**, **`docker stop`**, **`docker rm`**, etc.

- **Description**: Docker container is an instance of a Docker image that runs as a lightweight, isolated process on the host system.
- **Example**: When you run a Docker image, it creates a container based on that image.
- **Code**: To list running containers, you can use the following command
    
    ```bash
    docker ps
    ```
    

1. **Isolation**: Docker containers provide process isolation, meaning each container operates as an independent process, isolated from other containers and the host system. This isolation ensures that applications running within containers do not interfere with each other, providing a high level of security and stability.
2. **Image-Based**: Containers are created from Docker images, which are read-only templates that contain the application and all its dependencies. Images can be built either from scratch or by layering new changes on top of existing images. This layered approach allows for efficient image distribution and minimizes redundancy.
3. **Portability**: Docker containers can run on any system that supports the Docker runtime, regardless of the underlying infrastructure. This portability makes it easy to deploy applications across different environments, such as development, testing, staging, and production, without worrying about compatibility issues.
4. **Efficiency**: Docker containers are lightweight and consume fewer resources compared to traditional virtual machines (VMs). Since containers share the host system's kernel, they require less overhead and can be started and stopped quickly, making them ideal for scaling applications and microservices architectures.
5. **Orchestration**: Docker provides tools like Docker Swarm and Kubernetes for orchestrating containerized applications at scale. These tools automate the deployment, scaling, and management of containers, making it easier to manage complex containerized environments.
6. **Version Control**: Docker images are version-controlled, allowing developers to track changes and roll back to previous versions if necessary. This version control ensures consistency across different environments and simplifies the deployment process.
7. **Dependency Management**: Docker containers encapsulate dependencies within the image, eliminating conflicts between different versions of libraries or runtime environments. This dependency management streamlines the development and deployment process, reducing the likelihood of compatibility issues.