# Swarms

* **Swarm** = “Dockerized” cluster, group of machines(=nodes) (physical/virtual) running Docker joined into a cluster.

* **Swarm manager:**
  * Load ballancer on a cluster
  * Different strategies: Emptiest node, Global (each machine - one instance), ...
  * Only machine in a swarm that can execute your commands or add other machines as workers.
  * **Worker:** only provide computing capacity.

