# About Docker
## What is Docker?
Docker is a *containerization* platform.

<img src="./images/docker-logo.png" alt="Docker Logo" width="300" />

  **Containerization**: The process of packaging source code into an executable container
  - Kubernetes is used by larger infrastructures and requires at least 3 servers to run applications
  - Docker is best for individual users and smaller infrastructures, requires only 1 server
  
  **Container**: The executable, packaged source code/software. Similar to a Virtual Machine (VM), but does not simulate an entire computer
  
  **Registry**: Stores and distributes named Docker images, organized into repositories. Repositories hold versions of an image, identified by tags
  - Docker Hub is the official, public registry, and is used by default
  
  **Image**: Similar to a snapshot for VMs, it acts as a static template for containers
  
  **Layer**: The difference between an old and new image, manually created after using <code>docker commit</code> to commit file changes
  - <code>docker commit [options/flags] CONTAINER [REPOSITORY[:TAG]]</code>
  - NOTE: images are static (you cannot edit them), so any changes made must be saved to a new image!

  **Docker Daemon**: The background process running on the OS, executing Docker tasks. Configured using the Docker Desktop settings page, or through a JSON file

  **Docker Client**: The primary way of interacting with Docker. The Client sends commands to <code>dockerd</code> (the Docker daemon)
  - Client can communicate to multiple daemons
  
## How to Use Docker
### Setup
1. [Download Docker](https://www.docker.com/get-started/) for your OS
2. Test installation by running <code>docker run hello-world</code>

### Running a Container
1. <code>docker pull example-image-here</code> to pull an image from the *Docker registry*
2. <code>docker run example-image-here echo "success message here"</code> to run an image, then echo a message for user-readable feedback
   - Docker container will run and then exit very quickly, so adding a message is useful for notifying the user

## Example Docker Commands
<code>docker images</code>
- lists images on the system
  
| REPOSITORY | TAG | IMAGE ID | CREATED | VIRTUAL SIZE |
| --- | --- | --- | --- | --- |

<code>docker ps</code>
- lists containers that are running
- <code>docker ps -a</code> will show all containers, including ones that have exited
  
| CONTAINER ID | IMAGE | COMMAND | CREATED | STATUS | PORTS | NAMES |
| --- | --- | --- | --- | --- | --- | --- |

