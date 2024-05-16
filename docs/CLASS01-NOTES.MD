#Class 01 - DC-001

Commands used:
  - docker compose up: This command is used to create and start containers based on your docker-compose.yml file.

  - docker compose down: This command stops running containers and removes containers, networks, volumes, and images that were created by docker compose up.

Compose Sintax:

services:
  nginx:
    image: nginx:latest
    ports:

services:: This section defines the services that make up your application. In your case, there’s a single service named nginx.

nginx:: This is the name of the service. You can choose any name you like. It corresponds to the container that will be created based on the specified configuration.

image: nginx:latest: This line specifies the Docker image to use for the nginx service. In this case, it uses the official nginx image with the latest tag. The latest tag means it will pull the most recent version of the nginx image from the Docker Hub.

ports:: This section allows you to map ports between the host machine and the container. However, in your provided snippet, the ports section is empty. You would typically specify port mappings here, such as:

ports:
  - "8080:80"

This example maps port 8080 on the host to port 80 inside the nginx container.