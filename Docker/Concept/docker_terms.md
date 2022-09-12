Overview
-------------------------
Docker is a software development tool and virtualization technology that makes it easy to develop, deploy and manage applications using containers. It uses OS/Kernel virtualization

+ Docker is based on Linux Containers (LXC) which relies on two kernel mechanism : Control groups and Namespaces 
+	Docker provides isolated workspace for all its containers through Namespaces (It provides a container with its own linux system)
+	CGroups allocates and limits resources such as CPU, memory. They restrict the container processes from too much utilization of Host machine’s resources

Architecture
--------------

![image](https://user-images.githubusercontent.com/103237142/189567425-4f59921d-e083-4c6b-a066-56f933f8564d.png)

Docker follows client-server architecture:

**Docker Client**: It takes input/commands from user and gets the response from daemon

**Docker Daemon**: It builds, runs, and ships containers and can exist on same or different hosts

**Docker Engine**: It is a packaging tool which provides workflow for building and containerizing your application

**Docker Hub**: It hosts a registry to upload and manage your apps

**Docker Images**: It is a read-only template to create containers

**Docker Registry**: It holds images in public or private store

**Docker Container**: It holds applications along with dependencies 


Docker Images: A package which consists of an application binaries with all its dependencies and configuration files needed to run the code. Docker image can have series of layers, each layer represents an instruction that we run

Docker root directory:` /var/lib/docker`

Credentials are stored in `/root/.docker/config.json`





