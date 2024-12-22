# Docker

> Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime.



## useful docker commands

> TIP: __run a new container (nginx as an example)__
>
> - search nginx in docker hub
> ```bash
> $ docker search nginx
>
> NAME                               DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
> nginx                              Official build of Nginx.                        19946     [OK]
> bitnami/nginx                      Bitnami container image for NGINX               189                  [OK]
> nginxinc/nginx-unprivileged        Unprivileged NGINX Dockerfiles                  152
> nginxproxy/nginx-proxy             Automated nginx proxy for Docker containers …   138
> ```
>
> - ...and pull the image
> ```bash
>  docker pull nginx
> ```
>
> - ... and start a new container from an Image
> ```bash
> docker run IMAGE
> docker run nginx
> ```
>
> - ...and assign it a name
> ```bash
> docker run --name CONTAINER IMAGE
> docker run --name CONTAINER nginx
> ```
>
> - ...and map ports
> ```bash
> docker run -p HOSTPORT:CONTAINERPORT IMAGE
> docker run -p 8080:80 nginx
> ```
>
> - ...and map all ports
> ```bash
> docker run -P IMAGE
> docker run -p nginx
> ```
>
> - ...and start container in background
> ```bash
> docker run -d IMAGE
> docker run -d nginx
> ```
>
> - ...and assign it a hostname
> ```bash
> docker run --hostname HOSTNAME IMAGE
> docker run --hostname srv nginx
> ```
> - ...and add a dns entry
> ```bash
> docker run --add-host HOTNAME:IP IMAGE
> ```
>
> - ...and map a local directory into the container
> ```bash
> docker run -v HOSTDIR:TARGETDIR IMAGE
> docker run -v ~/:/usr/share/nginx/html nginx
> ```
>
> - ...but change the entrypoint:
> ```bash
> docker run -it --entrypoint EXECUTABLE IMAGE
> docker run -it --entrypoint bash nginx
> ```
>
> _👤 Anis Tajouri (Q2 2024)_


> TIP: __manage containers__
>
> - Show a list of running containers:
> ```bash
> docker ps
> ```
>
> - Show a list of all containers
> ```bash
> docker ps -a
> ```
> - Delete a container
> ```bash
> docker rm CONTAINER
> docker rm web
> ```
>
> - Delete a running container
> ```bash
> docker rm -f CONTAINER
> docker rm -f web
> ```
>
> - Delete stopped containers
> ```bash
> docker container prune
> ```
>
> - Stop a running container
> ```bash
> docker stop CONTAINER
> docker stop web
> ```
>
> - tart a stopped container
> ```bash
> docker start CONTAINER
> docker start web
> ```
>
> - Copy a file from a container to the host
> ```bash
> docker cp CONTAINER: SOURCE TARGET
> docker cp web:/index.html index.html
> ```
>
> - Copy a file from the host to a container
> ```bash
> docker cp TARGET CONTAINER: SOURCE
> docker cp index.html web:/index.html
> ```
>
> - Start a shell inside a running container
> ```bash
> docker exec -it CONTAINER EXECUTABLE
> docker exec -it web bash
> ```
>
> - Rename a container
> ```bash
> docker rename OLD_NAME NEW_NAME
> docker rename 096 web
> ```
>
> - Create an image out of container
> ```bash
> docker commit CONTAINER
> docker commit web
> ```

> TIP: __manage container images__
>
> - Download an image
> ```bash
> docker pull IMAGE[ : TAG]
> docker pull nginx
> ```
>
> - Upload an image to a repository
> ```bash
> docker push IMAGE
> docker push myimage :1.0
> ```
>
> - Delete an image
> ```bash
> docker rmi IMAGE
> ```
>
> - Show a list of all Images
> ```bash
> docker images
> ```
>
> - Delete dangling images
> ```bash
> docker image prune
> ```
>
> - Delete all unused images
> ```bash
> docker image prune -a
> ```
>
> - Build an image from a Dockerfile
> ```bash
> docker build DIRECTORY
> docker build .
> ```
>
> - Tag an image
> ```bash
> docker tag IMAGE NEWIMAGE
> docker tag ubuntu ubuntu: 18.04
> ```
>
> - Build and tag an image from a Dockerfile
> ```bash
> docker build -t IMAGE DIRECTORY
> docker build -t myimage .
> ```
>
> - Save an image to tar file
> ```bash
> docker save IMAGE > FILE
> docker save nginx > nginx.tar
> ```
>
> - Load an image from a .tar file
> ```bash
> docker load -i TARFILE
> docker load -i nginx.tar
> ```

> TIP: __getting infos and stats__
>
> - Show the logs of a container
> ```bash
> docker logs CONTAINER
> docker logs web
> ```
>
> - Show stats of running containers
> ```bash
> docker stats
> ```
>
> - Show processes of container
> ```bash
> docker top CONTAINER
> docker top web
> ```
>
> - Show installed docker version
> ```bash
> docker version
> ```
>
> - Get detailed info about an object
> ```bash
> docker inspect NAME
> docker inspect nginx
> ```
>
> - Show all modified files in container
> ```bash
> docker diff CONTAINER
> docker diff web
> ```
>
> - Show mapped ports of a container
> ```bash
> docker port CONTAINER
> docker port web
> ```
