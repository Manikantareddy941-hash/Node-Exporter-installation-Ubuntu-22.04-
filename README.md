# Node Exporter Installation (Ubuntu 22.04)

## What is Node Exporter?
Node Exporter collects system metrics like CPU, RAM, disk, and network for Prometheus.

## Install Steps

sudo useradd --system --no-create-home --shell /bin/false node_exporter

cd /tmp
wget https://github.com/prometheus/node_exporter/releases/download/v1.6.0/node_exporter-1.6.0.linux-amd64.tar.gz
tar -xvf node_exporter-1.6.0.linux-amd64.tar.gz
sudo mv node_exporter-1.6.0.linux-amd64/node_exporter /usr/local/bin/
rm -rf node_exporter*

## Create service
sudo nano /etc/systemd/system/node_exporter.service

(Add service config)

## Start
sudo systemctl enable node_exporter
sudo systemctl start node_exporter

## Metrics URL
http://<server-ip>:9100/metrics
