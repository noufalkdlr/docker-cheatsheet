# docker-cheatsheet 🐳

A collection of basic Docker commands for beginners.

## 1. Images 📦
*An Image is the blueprint or package of the software.*

- **Download an Image:**
  Pull the latest Ubuntu image from Docker Hub.
  ```bash
  docker pull <image_name>
  # Example: docker pull ubuntu
  ```

- **List Images:**
  Show all the images currently downloaded on your system.
  ```bash
  docker images
  ```

  -**Delete an Image:**
  Remove an image from your local storage to save space.
  ```bash
  docker rmi <image_name>
  # Example: docker rmi ubuntu
  ```
  
## 2. Containers 🚀
  A Container is a running instance of an Image.
  
  - **Run a Container (Basic):**
    This starts the container, executes a command (if any), and then exits immediately.
    ```bash
    docker run <image_name>
    # Example: docker run ubuntu
     ```

  - **Interactive Mode:**
    Most Useful Start a container and enter its terminal shell.
    -  `-i`: Interactive (keeps STDIN open)
    -  `-t`: Pseudo-TTY (allocates a terminal)
    ```bash
    docker run <image_name>
    # Example: docker run ubuntu
     ```    
    
