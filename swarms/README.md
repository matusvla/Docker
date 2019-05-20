# Swarms

* **Swarm** = “Dockerized” cluster, group of machines(=nodes) (physical/virtual) running Docker joined into a cluster.

* **Swarm manager:**
  * Load ballancer on a cluster
  * Different strategies: Emptiest node, Global (each machine - one instance), ...
  * Only machine in a swarm that can execute your commands or add other machines as workers.
  * **Worker:** only provide computing capacity.

* Initialize swarm and make your current machine a swarm manager: `docker swarm init`

* Join swarm as a worker: `docker swarm join`

* Create two VMs to simulate swarm behavior:
```
docker-machine create --driver virtualbox myvm1
docker-machine create --driver virtualbox myvm2
```

* List machines and show their IP addresses: `docker-machine ls`

* Send command to machine: `docker-machine ssh`
  * Initialize VM1 as swarm manager: `docker-machine ssh myvm1 "docker swarm init --advertise-addr <swarmManagerIPAddress>"`
  * Add a worker: `docker-machine ssh myvm2 "docker swarm join --token <SWM...> <workerIPAddress>:2377"`
  * Display nodes in the swarm: `docker-machine ssh myvm1 "docker node ls"`

* Configure current shell to talk directly to the Docker daemon on myvm1 (no need for ssh): `docker-machine env myvm1` and run the advised command.
  * Check using `docker-machine ls`, myvm1 has `*` in `ACTIVE`
  * After this you can deploy the app using: `docker stack deploy -c ../servicesIntro/docker-compose.yml swarmapp` and use normal commands.

* *NOTE:* Always run swarm init or swarm join with port 2377 (is default), port 2376 is docker daemon port

