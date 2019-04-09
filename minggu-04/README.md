# Docker Network Configuration Tutorial

## 1. [Communicating Between Containers](communicating-between-containers.md)

This scenario explores how to allow multiple containers to communicate with each other. The steps will explain how to connect a data-store, in this case, Redis, to an application running in a separate container.

This environment has been configured with a Docker client and daemon. The machine name the Docker daemon is running on is called docker. If you want to access any of the services, then use docker instead of localhost or 0.0.0.0.

[**Katacoda**](https://www.katacoda.com/courses/docker/5) Communicating Between Containers

## 2. [Docker Networks](docker-networks.md)

This scenario explores how to create a docker network allowing containers to communicate. We'll also explore the Embedded DNS Server added in Docker 1.10.

Docker has two approaches to networking. The first defines a link between two containers. This link updates /etc/hosts and environment variables to allow containers to discover and communicate.

The alternate approach is to create a docker network that containers are connected to. The network has similar attributes to a physical network, allowing containers to come and go more freely than when using links.

[**Katacoda**](https://www.katacoda.com/courses/docker/networking-intro) Docker Networks