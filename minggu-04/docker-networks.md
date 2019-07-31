![](images/dn/1.png)

# Docker Networks

## 1 - Create Network

The first step is to create a network using the CLI. This network will allow us to attach multiple containers which will be able to discover each other.

## Create Network

To start with we create the network with our predefined name. 

![](images/dn/2.png)

## Connect To Network

When we launch new containers, we can use the --net attribute to assign which network they should be connected to. 

## 2 - Network Communication

Unlike using links, docker network behave like traditional networks where nodes can be attached/detached.

![](images/dn/3.png)

![](images/dn/4.png)

Instead, the way containers can communicate via an Embedded DNS Server in Docker. This DNS server is assigned to all containers via the IP 127.0.0.11 and set in the resolv.conf file.

![](images/dn/5.png)

When containers attempt to access other containers via a well-known name, such as Redis, the DNS server will return the IP address of the correct Container. In this case, the fully qualified name of Redis will be redis.

![](images/dn/6.png)

## 3 - Connect Two Containers

Docker supports multiple networks and containers being attached to more than one network at a time.

For example, let's create a separate network with a Node.js application that communicates with our existing Redis instance.

The first task is to create a new network in the same way.

![](images/dn/7.png)

When using the connect command it is possible to attach existing containers to the network.

![](images/dn/8.png)

When we launch the web server, given it's attached to the same network it will be able to communicate with our Redis instance.

![](images/dn/9.png)

Test it using

![](images/dn/10.png)

## 4 - Create Aliases

Links are still supported when using docker network and provide a way to define an Alias to the container name. This will give the container an extra DNS entry name and way to be discovered. When using --link the embedded DNS will guarantee that localised lookup result only on that container where the --link is used.

## Connect Container with Alias.
The following command will connect our Redis instance to the frontend-network with the alias of db.

![](images/dn/11.png)

When containers attempt to access a service via the name db, they will be given the IP address of our Redis container.

![](images/dn/12.png)

## 5 - Disconnect Containers

With our networks created, we can use the CLI to explore the details.

The following command will list all the networks on our host.

![](images/dn/13.png)

We can then explore the network to see which containers are attached and their IP addresses.

![](images/dn/14.png)

The following command disconnects the redis container from the frontend-network.

![](images/dn/15.png)
