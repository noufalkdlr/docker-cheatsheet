# docker-cheatsheet 🐳

A collection of basic Docker commands for beginners.

## 1. Images 📦
*An Image is the blueprint or package of the software.*

- **Download an Image:**
  Pull the latest Ubuntu image from Docker Hub.
  ```bash
  docker pull ubuntu
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
