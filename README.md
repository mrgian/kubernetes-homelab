# Kubernetes Homelab

Kubernetes (and nginx) configuration files for my [home server](https://gian.im/posts/homeserver/)

Each yaml yaml file contains **deployment** and **service** configurations for the corresponding app.

## Reverse proxy

I use this in **Minikube**, so every NodePort service is used to expose the app outside the Minikube node. Nginx is configured as reverse proxy to those ports, so that the services are publicly exposed.

For example *cloud.gian.im* is a reverse proxy to *http://192.168.49.2:30001*, where *192.168.49.2* is the node IP and *30001* is the port exposed by the service.

## Volume mounts

Persistent directories are mounted to */home/docker/data* in the Minikube node. If you want to access this directory from the host machine you can mount it running Minikube with this command:

`minikube start --mount --mount-string="/home/gian/data:/home/docker/data"`

## App list and services ports
- **Nextcloud** (file hosting) on port *30001*
- **Vaultwarden** (password manager) on port *30002*
- **Minecraft** (multiplayer server) on port *30003*
- **DynMap** (live map for Minecraft) on port *30004*
- **Invidious** (YouTube alternative front-end) on port *30005*
- **Kubernets Dashboard** (web interface for k8s) on port *30006*
- **Home Assistant** (smart home automation) on port *30007*
- **Photoprism** (photo gallery) on port *30008*
- **Pi-Hole** (DNS server) on port *30009*
