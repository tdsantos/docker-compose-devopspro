#Class 02 - DC-002

Commands used:
  - docker compose up:
  - docker compose down: 

Compose Sintax:

environment:

In a docker-compose file, the environment section is used to define environment variables for services. These variables can be set directly in the file or referenced from an external .env file. Here’s a brief explanation:

- Direct Definition: You can specify environment variables directly within the docker-compose.yml file under the environment key for a service. This method is straightforward and allows you to set different environment variables for each service.

- Using .env File: Alternatively, you can use an .env file placed at the root of the project directory. This file contains key-value pairs of environment variables that are made available to the containers when you run docker-compose up. The .env file is useful for centralizing configuration and managing multiple environment variables.

- Variable Substitution: Docker Compose supports variable substitution, which allows you to use values from the .env file within your docker-compose.yml. For example, if you have DEBUG=1 in your .env file, you can reference it in your docker-compose.yml like this:

services:
  webapp:
    image: my-webapp-image
    environment:
      - DEBUG=${DEBUG}

env_file Attribute: You can also specify one or more .env files using the env_file attribute in your docker-compose.yml. Docker Compose will read the variables from the files in the order specified, and the last definition of a variable takes precedence.

Tips:

After you execute docker-compose uo and receive a message that ou have orphan containers you need to execute the command with "--remove-orphans" parameter. It's occurs when you modified de entire structure of a compose file.

exampe: docker compose up -d --remove-orphans