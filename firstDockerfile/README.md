# First Dockerfile

https://docs.docker.com/get-started/part2/

* Create image: `docker build --tag=friendlyhello .`
  
* Map your machine’s port 4000 to the container’s published port 80 and run the image: `docker run -d -p 4000:80 friendlyhello`
  
* Display list of all containers: `docker container ls`
  * `-q` just for container ids
  
* Display list of all images: `docker image ls`

* Stop container with the specified id: `docker container stop 1fa4ab2cf395`

* Log in to Dockerhub: `docker login`

* Associate local image with image on the Dockerhub: `docker tag friendlyhello vladislavmatus/first-dockerfile:1.0`

* Remove all dangling resources: `docker system prune -a`
