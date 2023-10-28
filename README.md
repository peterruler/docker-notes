# docker-notes

# Youtube ressource
- Based on a youtube tutorial by Chistian Lempa
- https://www.youtube.com/watch?v=Nm1tfmZDqo8

# install docker desktop for testing
- https://docker.com/get-started

# install docker on specific linux
- https://docs.docker.com/engine/install/ubuntu/

# install docker on ubuntu

```
sudo apt-get remove docker docker-engine docker.io

sudo apt-get update

sudo apt install docker.io

sudo apt install docker-compose # is different to macos
```

# test docker
- `docker` output shows options
- `docker version` to check that docker is correctly installed

# start a test- / demo-container
- `docker run hello-world`
- (do a stop and rm of this container)

# run a image enter shell in the container
- `docker run --interactive --tty debian`
- `docker run --interactive --tty centos`

# nginx webserver
- https://hub.docker.com/_/nginx
- `docker pull nginx:1.24.0` install a specific version of nginx
- `docker run nginx:latest` always use the latest stable version of nginx

# list images
- `docker image ls`

# delete images
- `docker rmi b038788ddb22` short for `docker image rm <imghash>` - remove image from system

# run a specfic nginx version
- `docker run nginx:1.24.0`

# list containers
 - `docker ps`
 - `docker ps --all` list also nonstarted containers

 # info about container
 - `docker inspect busy_wilbur` busy_wilbur container name, to get the ip of the container for example.

 # for production
- chose desired name e.g. nginx-prod-1 by using the `--name` flag
- `-d` for detached run webserver in background
- `-p` for --publish port containerinternal:hostport
- `-v` for --volume mountpoints or volumes mapping internalcontainer:hostsystem

# start a production instance of nginx in background
- The complete start docker command to start a webserver
- `docker run --name nginx-prod-1 -p 80:80 -p 443:443 -v /Users/peterstroessler/Sites:/usr/share/nginx/html -d nginx:1.25.2`
- replace `/Users/peterstroessler/Sites` with the path on your machine containing the html files

# have an index.html in your mapped directory 
- have a index html in the local directory on my machine `/Users/peterstroessler/Sites` have a sample index.html in there

# test the webserver in the terminal
- `curl localhost` to test in a terminal

# call in webbrowser to test
- call `http://localhost`