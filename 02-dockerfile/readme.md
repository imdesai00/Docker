- A Dockerfile is a text file that contains a set of instructions for building a Docker image. Each instruction in the Dockerfile represents a step in the image creation process.
- Common instructions include **`FROM`** (specifying the base image), **`RUN`** (executing commands inside the image), **`COPY`** (copying files into the image), **`EXPOSE`** (specifying ports to expose), **`CMD`** (defining the default command to run when a container starts), and more.

- **Description**: Dockerfile is a text file that contains instructions for building a Docker image. It specifies the base image, dependencies, and commands to set up the application environment.
- **Example**: Below is an example Dockerfile for a simple Node.js application
    
    ```bash
    # Use the official Node.js image as the base image
    FROM node:14
    
    # Set the working directory in the container
    WORKDIR /app
    
    # Copy package.json and package-lock.json to the working directory
    COPY package*.json ./
    
    # Install dependencies
    RUN npm install
    
    # Copy the rest of the application code to the working directory
    COPY . .
    
    # Expose port 3000
    EXPOSE 3000
    
    # Command to run the application
    CMD ["node", "app.js"]
    
    ```
    
- **Code**: Save the above Dockerfile in the root directory of your Node.js application and run the following command to build the Docker image:
    
    ```bash
    docker run my-node-app
    ```
    
    ### **1. Base Image**
    
    ```bash
    FROM <base_image
    ```
    
    Specifies the base image on which your image is built. This is typically the starting point for your image and provides the foundation environment.
    
    ### **2. Maintainer Information**
    
    ```bash
    MAINTAINER <maintainer_name>
    ```
    
    Specifies the author/maintainer of the Dockerfile. This command is deprecated in favor of using **`LABEL`** for metadata.
    
    ### **3. Environment Variables**
    
    ```bash
    ENV <key> <value>
    ```
    
    Sets environment variables within the Docker image. These variables can be accessed during the build process or when running a container from the image.
    
    ### **4. Working Directory**
    
    ```bash
    WORKDIR /path/to/directory
    ```
    
    Sets the working directory for any **`RUN`**, **`CMD`**, **`ENTRYPOINT`**, **`COPY`**, and **`ADD`** instructions that follow in the Dockerfile.
    
    ### **5. Copy Files/Directory**
    
    ```bash
    COPY <src> <dest>
    ```
    
    Copies files or directories from the host machine to the Docker image.
    
    ### **6. Add Files/Directory**
    
    ```bash
    ADD <src> <dest>
    ```
    
    Similar to **`COPY`**, but also supports fetching files from remote URLs and extracting compressed archives.
    
    ### **7. Run Commands**
    
    ```bash
    RUN <command>
    ```
    
    Executes commands in the Docker image during the build process. These commands are typically used to install packages, configure the environment, and set up the application.
    
    ### **8. Expose Ports**
    
    ```bash
    EXPOSE <port>
    ```
    
    Informs Docker that the container listens on specific network ports at runtime. It does not actually publish the port, but documents which ports are intended to be published.
    
    ### **9. Define Commands to Run**
    
    ```bash
    CMD ["executable", "param1", "param2"]
    CMD command param1 param2
    ```
    
    Specifies the command to run when a container is started from the image. If there are multiple **`CMD`** instructions, only the last one will take effect.
    
    ### **10. Define Entrypoint**
    
    ```bash
    ENTRYPOINT ["executable", "param1", "param2"]
    ENTRYPOINT command param1 param2
    ```
    
    Similar to **`CMD`**, but provides a fixed starting command for the container. The **`CMD`** parameters will be passed as arguments to the **`ENTRYPOINT`** command.
    
    ### **11. Define Metadata**
    
    ```bash
    LABEL key="value"
    ```
    
    Adds metadata to the image. This can include information such as version, description, author, etc. It's useful for documentation and organization.
    
    ### **12. Set User**
    
    ```bash
    USER <username or UID>
    ```
    
    Sets the user that the image should run as when it's executed as a container. This can be a username or a UID.
    
    ### **13. Define Dockerfile Build Time Arguments**
    
    ```bash
    ARG <name>[=<default_value>]
    ```
    
    Defines build-time variables that can be used in the **`Dockerfile`**. These values can be overridden during the build process using the **`--build-arg`** flag with the **`docker build`** command.