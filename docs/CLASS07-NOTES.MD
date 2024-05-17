Commands learned in this class:

- docker system prune ==> This command removes all unused containers, networks, images (both dangling and unused), and optionally, volumes. It’s a way to clean up disk space by removing resources that are no longer in use by any containers1.

- docker compose pull ==> This command is used within the context of Docker Compose to pull service images as defined in a docker-compose.yml file. It does not start the containers but ensures that the images for the services are downloaded and ready


- docker compose up -d --build ==>  The docker compose up command starts and runs the entire application as defined in the docker-compose.yml file. The -d flag runs the containers in detached mode (in the background). The --build option ensures that the images for the services are built or rebuilt before starting the containers. This is useful when you have made changes to the services or their Dockerfiles and want to update the images before running them

Parameters learned:

Stage build

    build:
      context: ./src
      dockerfile: Dockerfile

The build parameter in Docker Compose is used to specify the configuration for building an image as part of a service definition in the docker-compose.yml file. It can be defined in two ways:

As a simple string specifying the path to the build context (where the Dockerfile and associated files are located):

- build: ./path/to/build/context

As a complex object that includes additional options such as context, dockerfile, args, and more:

build:
  context: ./path/to/build/context
  dockerfile: Dockerfile-alternate
  args:
    - ARG1=value1
    - ARG2=value2

Here’s what each sub-parameter means:

- context: The path to the directory containing the Dockerfile and any other files needed for the build. It can be a relative path from the location of the docker-compose.yml file or an absolute path1.

- dockerfile: Specifies the Dockerfile to use. It can be a file name if located in the build context or a relative path to the build context1.

- args: Allows you to specify build-time variables referenced in the Dockerfile2.
When you run docker compose up and include the --build flag, it will use the build parameter from the docker-compose.yml file to build or rebuild services before starting containers2. This is particularly useful when you want to incorporate changes made in the Dockerfile or the application code
