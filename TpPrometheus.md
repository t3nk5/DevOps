EX 1
docker pull prom/prometheus:latest

docker run -d --name prometheus -p 9090:9090 prom/prometheus:latest

docker ps

http://localhost:9090

<img width="2742" height="500" alt="image" src="https://github.com/user-attachments/assets/ef15fdb8-4631-4163-84b4-067a7069f066" />

docker logs prometheus

<img width="1949" height="64" alt="image" src="https://github.com/user-attachments/assets/721d5f7c-00a6-47dc-9c61-c1d42f4982a7" />


EX2

docker rm -f prometheus
mkdir prometheus-lab
cd prometheus-lab

nano prometheus.yml

global:
  scrape_interval: 10s

  external_labels:
    environment: lab

scrape_configs:
  - job_name: "prometheus"

    static_configs:
      - targets: ["localhost:9090"]
   
        
       
docker run -d `
  --name prometheus `
  -p 9090:9090 `
  -v "${PWD}\prometheus.yml:/etc/prometheus/prometheus.yml" `
  prom/prometheus:latest `
  --config.file=/etc/prometheus/prometheus.yml `
  --web.enable-lifecycle


Invoke-WebRequest -Method POST http://localhost:9090/-/reload
<img width="2710" height="190" alt="image" src="https://github.com/user-attachments/assets/f8a2907b-d048-4b52-8dae-5eae9ab92975" />
<img width="869" height="390" alt="image" src="https://github.com/user-attachments/assets/3e64e0c7-a0a9-4727-8ce6-d957d2f07439" />


docker run -d --name node-exporter -p 9100:9100 prom/node-exporter:latest
nano prometheus.yml

global:
  scrape_interval: 10s

  external_labels:
    environment: lab

scrape_configs:
  - job_name: "prometheus"
    static_configs:
      - targets: ["localhost:9090"]

  - job_name: "node"
    static_configs:
      - targets: ["host.docker.internal:9100"]



<img width="2698" height="250" alt="image" src="https://github.com/user-attachments/assets/a17060fa-44c9-4c72-9c0e-f6916fe3016d" />

<img width="2738" height="554" alt="image" src="https://github.com/user-attachments/assets/5a86a064-1370-4d44-8a96-f5ce5632600e" />

