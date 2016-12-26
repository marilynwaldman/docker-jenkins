eval "$(docker-machine env default)"

This Dockerfile was created as the Jenkins docker image on DockerHub does not have sudo and therefore you cannot
add packages to the image.  It is borrowed from:


http://container-solutions.com/running-docker-in-jenkins-in-docker/

1.git clone this repo.
2.cd to the directory jenkins-docker
3 docker build -t myjenkins
4. docker run -d -v /var/run/docker.sock:/var/run/docker.sock \
                -v $(which docker):/usr/bin/docker -p 8090:8080 myjenkins

point the browser to port 8090.

