# Instalación del Stack de Monitoreo!

Instalación con Docker

## Node-Exporter

`docker run -d -p 9100:9100 --name node-exporter -h node-exporter --net host prom/node-exporter`

## Alert Manager

`cd alertmanager \`

`docker build -t cindi-alertmanager . \`

`docker run -d -p 9093:9093 --name alertmanager --net host cindi-alertmanager \`

## Prometheus

`cd prometheus \ `

`docker build -t cindi-prometheus . \`

`docker run -p 9090:9090 -h prometheus --net host --name prometheus -d cindi-prometheus`

## Grafana

`cd grafana`

`docker build -t cindi-grafana . \`

`docker run -d -v /var/lib/grafana --name grafana-storage --net host busybox:latest \`

`docker run -d -p 3000:3000 --name=grafana --net host -h grafana --volumes-from grafana-storage   cindi-grafana

### URLs

> **Grafana:** [http://localhost:3000](http://localhost:3000)
>>**User:** admin 
>>**Password:** admin

> **Prometheus:** [http://localhost:9090](http://localhost:9090)
> **Node-Exporter:** [http://localhost:9100](http://localhost:9100)
> **Alert Manager:** [http://localhost:9093](http://localhost:9093)
