- Volumes: In Docker, a volume is used to persist data across container lifecycles and for sharing data between containers. The syntax for defining a bind mount type of volume is as follows:

volumes:
  - type: bind
    source: <path_on_host>
    target: <path_in_container>

type: Specifies the type of volume, which can be bind, volume, or tmpfs. For bind mounts, type is set to bind.

source: The path on the host machine.

target: The path where the file or directory is mounted in the container.

Bind mounts are very performant and are useful when you need to store files on the host system outside the Docker environment1.

- Networks: Docker’s networking subsystem is pluggable, using different network drivers to provide various networking capabilities. Here’s a brief overview of the network drivers:

bridge: The default network driver. Used when containers need to communicate on the same Docker host2.

host: Removes network isolation between the container and the Docker host, using the host’s networking directly2.

overlay: Connects multiple Docker daemons together and enables containers to communicate across different hosts2.

ipvlan: Allows users to have total control over both IPv4 and IPv6 addressing2.

macvlan: Assigns a MAC address to a container, making it appear as a physical device on the network2.

none: Completely isolates a container from the host and other containers2.

Each driver is suited for different use cases, and you can specify the driver when creating a network:

networks:
  my_network:
    driver: bridge

In this example, my_network is created with the bridge driver. You can replace bridge with any other driver according to your needs

- Tips:

I'm using WSL2 and I have many issues to connect Dbeaver in my host windows machine to the posgres running in WSL. In this case I'm use PG Admin to test the connection with database. To connect external DBeaver to Postgres I need do use a network with bridge driver, it's works for me.