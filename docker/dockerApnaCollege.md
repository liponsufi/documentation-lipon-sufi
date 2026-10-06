# 🐳 Docker Essentials & Quick Guide

## 📌 Core Concepts

| Concept | Description |
| :--- | :--- |
| **Image Sharing** | People share **Docker Images** (not running containers) via registries like Docker Hub. An image is a read-only template or blueprint. |
| **Resource Usage** | **Docker Containers** consume active system memory (RAM) and CPU resources when running, whereas images primarily consume disk storage. |

---

## 💻 Essential Docker Commands

### 1. Download Docker Image (`Download image`)
To download a Docker image from a registry to your local system, use the `pull` command:

```cmd
docker pull image_name
```
### 2. Run Container from the Image (`run container from image`)
To create and start a container using a downloaded Docker image, execute the following command in your terminal:

```cmd
docker run image_name
```
### 3. Run Container in Interactive Mode (`-it`)
To run a container interactively (so you can access its terminal shell and type commands directly inside it), use the following command:

```cmd
docker run -it image_name
```
### 4. List All Containers (`docker ps -a`)
To view a list of **all containers** on your system—including both currently running containers and those that have stopped—execute the following command:

```cmd
docker ps -a
```
### 5. List Running Containers (`docker ps`)
To view a list of **currently running containers** on your system, execute the following command:

```cmd
docker ps
```
### 6. Start an Existing Container (`docker start`)
To start a container that has already been created or previously stopped, use the following command:

```cmd
docker start container_id_or_name
```
### 7. To stop Container that already running now (`Docker Stop`)
```cmd
docker stop container_id_or_name
```
### 8. List Local Docker Images (`docker images`)
To view a list of all **Docker images** currently downloaded and saved on your local system, execute the following command:

```cmd
docker images
```
### 9. Delete a Stopped Container (`docker rm`)
To permanently delete or remove one or more **stopped containers** from your local system to free up storage, execute the following command:
```cmd
docker rm container_id_or_name
```
### ⚠️ Important Note: Order of Deletion (`Container vs. Image`)

When cleaning up your local Docker environment, you **must delete the container first** before you can delete its corresponding image. 

#### Why?
* Docker prevents you from deleting an image if there are any stopped or running containers dependent on it.
* If you try to delete an image directly while a container uses it, Docker will throw an error.

#### Correct Cleanup Sequence:
1. **Stop the container**
```cmd
docker stop container_id_or_name
```
2.  **Remove the container**
```cmd 
docker rm container_name_or_id
```
3. **Remove The Image**
```cmd
docker rmi image_name_or_id
```

### 10. Delete Local Docker Image (`docker rmi`)
To delete or remove one or more **Docker images** from your local system and free up disk space, execute the following command:

```cmd
docker rmi image_name_or_id
```
### 11. Run Container in Detached Mode (`docker run -d`)
To run a container in the background (detached mode) so that your terminal stays free and you can continue running other commands, use the following command:

```cmd
docker run -d image_name
```
### 12. Run Container with a Custom Name (`--name`)
By default, Docker assigns a random, generated name to your containers (e.g., `optimistic_lovelace` or `boring_turing`). To assign a custom, easy-to-remember name to your container when starting it, use the `--name` flag:

```cmd
docker run --name custom_container_name image_name
```

# 🥞 Docker Image Layers


```text
+---------------------------------------------------+
|               Container (Writable)                |  <-- Mutable (Changes happen here)
+---------------------------------------------------+
|               Layer 2 (Intermediate)              |  <-- Immutable (Read-Only)
+---------------------------------------------------+
|               Layer 1 (Intermediate)              |  <-- Immutable (Read-Only)
+---------------------------------------------------+
|               Base Layer (Operating System)       |  <-- Immutable (Read-Only)
+---------------------------------------------------+
```
# 💻 Essential Port Binding Commands

### 1. Run Container with Port Binding (`-p`)
To map a container's **internal** port to your **host machine's port**, use the `-p` flag:

```cmd
docker run -p 8080:80 image_name
```

# Troubleshoot Command
### 1. View Logs of a Container
To check the logs of a specific container,To Check Container Errors, use its ID or Name:

```cmd
docker logs container_id_or_name
```
### 2. Accessing a Running Container (`docker exec`)

The `docker exec` command allows you to run commands inside a running container. By combining it with `-it` (interactive terminal) and a shell, you can literally **step inside** the container's environment.

---
### ⚠️ Important Note (`if any container don't have the bin/bash then use the second command for those container`)
###  Using Bash (`bin/bash`)
```cmd
docker exec -it container_name_id bin/bash
```

```cmd
docker exec -it container_name_id sh
```

# 💻 Docker Network
### 🌐 List Docker Networks (`docker network ls`)

To view all the networks available in your Docker environment, execute the following command:

```cmd
docker network ls
```
### 🌐 Create a Custom Docker Network (`docker network create`)

To allow multiple containers to communicate with each other securely and easily by name, you can create a custom user-defined network using the following command:

```cmd
docker network create network_name
```
### 🗑️ Delete a Docker Network (`docker network rm`)

To delete one or more unused custom networks from your system, use the following command:

```cmd
docker network rm network_name_or_id
```