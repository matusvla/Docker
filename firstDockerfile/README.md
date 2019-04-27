# First Dockerfile

https://docs.docker.com/get-started/part2/

docker build --tag=friendlyhello .

docker run -d -p 4000:80 friendlyhello

docker container ls

docker container stop 1fa4ab2cf395

docker login

docker tag friendlyhello vladislavmatus/first-dockerfile:1.0

docker image ls

docker system prune -a