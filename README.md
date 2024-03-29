# Monitor Host and Containers 

This project describes how to install monitoring tools via docker and check your host and containers health status.

## Monitoring tools
| Tool | Version |Description | 
|------|---------|------------|
| [Grafana](https://grafana.com) | 6.3.3 | Useded for visualize the data |
| [Prometheus](https://prometheus.io) | 2.12 |Monitor and collect metrics |
| [Cadvisor](https://github.com/google/cadvisor) | 0.33 |Monitor containers |

## Prerequisites
* Linux server - tested on Ubuntu 18
* Docker and Docker-Compose

## Installation instruction
```sh
mkdir -p /opt/docker/
cd /opt/docker/
git clone https://github.com/idanshemesh/MonitorDocker.git
cd /opt/docker/MonitorDocker
```
Install Docker (Optional)
```sh
chmod +x installDocker.sh
./installDocker.sh
```
Build the monitoring stack
```sh
docker-compose up -d
```
## View your metircs
* Open Grafana - surf to: http://YOURSERVER:3000
* Type the user **admin** and the password **idans**  (Don't forget to chage it)

## Run a test pressure
* Install stress
``
sudo apt-get install stress
``
* Run some tests, ex: 
``
stress --cpu 8 --io 4 --vm 2 --vm-bytes 128M --timeout 10s
``

Enjoy :-)

Idan Shemesh
