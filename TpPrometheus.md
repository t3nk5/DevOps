#'EX 1'
docker pull prom/prometheus:latest

docker run -d --name prometheus -p 9090:9090 prom/prometheus:latest

docker ps

http://localhost:9090

<img width="2742" height="500" alt="image" src="https://github.com/user-attachments/assets/ef15fdb8-4631-4163-84b4-067a7069f066" />

docker logs prometheus

<img width="1949" height="64" alt="image" src="https://github.com/user-attachments/assets/721d5f7c-00a6-47dc-9c61-c1d42f4982a7" />


EX2

