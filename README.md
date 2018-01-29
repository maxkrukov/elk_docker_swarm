# Elasticsearch+logstash+kibana standalone
- docker swarm init --advertise-addr 127.0.0.1
- git clone https://github.com/maxkrukov/elk_docker_swarm.git
- cd elk_docker_swarm
- docker network create -d overlay elk 
- docker build nginx-proxy/. -t nginx-proxy:1.0
- htpasswd  nginx-proxy/nginx/htpasswd admin
- docker stack deploy -c compose_elk.yml elasticsearch
- iptables -I DOCKER-USER -i <public_interface> -p tcp -m multiport --dports 9200,9300,5000 -j DROP
- Go to   https://<your_ip>
