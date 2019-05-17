# Introduction to services

https://docs.docker.com/get-started/part3/

* Initialize swarm mode for natively managing a cluster of Docker Engines: `docker swarm init`

* Run the app under name servicesintro: `docker stack deploy -c docker-compose.yml servicesintro`

* Show list of services: `docker service ls`

* Show list of tasks in service `getstarted_lab` (task = single container running in specific service): `docker service ps getstartedlab_web`

* Show list of tasks in stack: `docker stack ps getstartedlab -q`

* Scaling the app, i.e. applying changes in docker-compose.yml: `docker stack deploy -c docker-compose.yml getstartedlab`

* Take down the application: `docker stack rm getstartedlab`

* And then take down the swarm:  `docker swarm leave --force`