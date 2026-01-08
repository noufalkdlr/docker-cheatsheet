# docker-cheatsheet 🐳

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

  - **Delete an Image:**
  Remove an image from your local storage to save space.
  ```bash
  docker rmi <image_name>
  # Example: docker rmi ubuntu
  ```
  
## 2. Containers 🚀
  *A Container is a running instance of an Image.*
  
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
    docker run -it <image_name>
    # Example:  docker run -it ubuntu
     ```
    (To leave the container, type `exit`).

## 3. Naming & Resuming Containers 🏷️
*Give your container a name to easily find and reuse it later.*

- **Run with a Custom Name:**
  Instead of getting a random name (like `jolly_beaver`), assign one yourself.
  ```bash
  docker run --name <custom_name> -it <image_name>
  # Example: docker run --name my-ubuntu -it ubuntu
  ```

- **Resume a Stopped Container:**
  If you exited a named container, use this to go back to the same state (saved files, etc.).

  ```bash
  docker start -ai <container_name>
  # Example: docker start -ai my-ubuntu
  ```

 ## 4. Overriding Default Commands (`/bin/bash`) 🐚 🏷️
 *Control what program starts when the container runs.*

 - **When `/bin/bash` is Optional (e.g., Ubuntu):**
   The Ubuntu image is configured to start a shell by default.
  
   ```bash
     docker run -it ubuntu
     # OR
     docker run --name my-ubuntu -it ubuntu
     # This automatically opens /bin/bash, so you don't need to type it.
   ```

- **When `/bin/bash` is Required (e.g., Python/Node):**
  Some images start their own program (like python console) by default. To get a system terminal instead, you must specify it.

  ```bash
  docker run -it python /bin/bash
  # OR
  docker run --name my-python -it python /bin/bash
  # Without /bin/bash, you would get the Python >>> console.
  # With /bin/bash, you get the terminal to run pip install, ls, etc.
  ```

## 5. Manage Containers 🛠️

- **List Running Containers:**
  Show only the containers that are currently active.
  ```bash
  docker ps
  ```

  - **List All Containers:**
    Show all containers, including those that have stopped or exited.
  ```bash
  docker ps -a
  ```

  - **Stop a Container:**
    Gracefully stop a running container.
  ```bash
  docker stop <container_id_or_name>
  # Example: docker stop my-ubuntu
  ```
  
  - **Remove a Container:**
    Delete a stopped container permanently.
  ```bash
  docker rm <container_id_or_name>
  # Example: docker rm my-ubuntu
  ```

## 6. Cleaning Up (Prune) 🧹
*Quickly remove unused containers and reclaim disk space.*

- **Remove All Stopped Containers:**
  Instead of removing containers one by one using `rm`, delete all stopped ones instantly.
  ```bash
  docker container prune
  ```
  (It will ask for confirmation (y/n). Type y to proceed).

- **Total System Cleanup (Dangerous but Effective):**
  This removes all stopped containers, unused networks, and "dangling" images (broken downloads).
  ```bash
  docker system prune
  ```

- **Remove Unused Images Also:**
  If you want to remove images that are not currently being used by any container (saves a lot of space).
  ```bash
  docker system prune -a
  ```

    
