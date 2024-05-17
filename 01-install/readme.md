## Install In Linux

1. **Update Package Index**: First, update the package index on your system to ensure you have the latest version of available packages.
    
    ```bash
    sudo apt update
    ```
    
2. **Install Required Packages**: Install the packages necessary to allow the use of Docker’s repository:
    
    ```bash
    sudo apt install apt-transport-https ca-certificates curl software-properties-common
    ```
    
3. **Add Docker’s GPG Key**: Add Docker’s official GPG key to your system:
    
    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    ```
    
4. **Add Docker Repository**: Add the Docker repository to your system’s software repository list:
    
    ```bash
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    
    ```
    
5. **Update Package Index Again**: Update the package index once more:
    
    ```bash
    sudo apt update
    ```
    
6. **Install Docker CE (Community Edition)**: Finally, install Docker CE by running:
    
    ```bash
    sudo apt install docker-ce
    ```
    
7. **Verify Docker Installation**: After installation, verify that Docker is installed correctly by running the following command:
    
    ```bash
    sudo docker --version
    ```
    
    This should display the installed version of Docker.
    
8. **Start and Automate Docker**: Start the Docker service and enable it to start on boot:
    
    ```bash
    sudo systemctl start docker
    sudo systemctl enable docker
    ```
    
    ## Install in Mac
    
    1. **Download Docker Desktop for Mac**:
    Visit the Docker Desktop download page: Docker Desktop for Mac (Docker Hub).
    2. **Download Docker Desktop**:
    Click the "Download from Docker Hub" button to download the Docker Desktop installer for macOS.
    3. **Install Docker Desktop**:
    Once the download is complete, open the downloaded **`.dmg`** file.
    4. **Drag Docker to Applications**:
    Drag the Docker icon to the Applications folder to install Docker on your Mac.
    5. **Launch Docker Desktop**:
    Open the Applications folder and click on Docker to launch it. You might need to grant permissions for Docker to run.
    6. **Log in or Sign up**:
    If you have a Docker Hub account, you can log in. If not, you can sign up for a new account.
    7. **Docker Desktop Setup**:
    Follow the prompts to complete the Docker Desktop setup. This may include granting additional permissions to Docker.
    8. **Start Docker Desktop**:
    After the setup is complete, Docker Desktop should start automatically. You should see the Docker icon in your menu bar.
    9. **Test Docker Installation**:
    Open Terminal and type **`docker --version`** to verify that Docker is installed correctly. You should see the Docker version information.