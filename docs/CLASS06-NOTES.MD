- depends_on: specifies that one service depends on another. Specifically, it indicates that a service requires another service to be started before it can start.

When you use docker-compose up, services are created in dependency order. In other words, services listed in depends_on are started before the dependent services.

Similarly, when you execute docker-compose stop, the dependent service is stopped after the service it depends on.