- git clone https://github.com/maxkrukov/elk_docker_swarm.git
- cd elk_docker_swarm
- docker network create -d overlay elk
- docker stack deploy -c compose_elk.yml elasticsearch

