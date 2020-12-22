# docker-compose-omv5-armhf
A set of docker-compose files to quickly and easily set up docker containers on an ARMHF device. 
This project can configure several stacks of docker images, organized thematically.


**Web stack**

 This stack will install allow you to expose the others stacks services on the web. This stack contains :
 
 - [DuckDNS](https://github.com/linuxserver/docker-duckdns)
 - [Nginx Proxy Manager](https://github.com/jc21/nginx-proxy-manager)


**Cloud stack**

 This stack will install the nextcloud cloud suite for ARM devices. This stacks contains : 

 - [NextCloud](https://github.com/nextcloud/docker)
 - [Redis](https://github.com/redis)
 - [MariaDB](https://github.com/JSurf/docker-rpi-mariadb)


**Book stack**

 This stack will install an ebook and a comics/manga/graphic-novel managment and reading portal. This stacks contains :
 
 - [Calibre-Web](https://github.com/linuxserver/docker-calibre-web)
 - [Komga](https://github.com/gotson/komga)


**Content fetcher stack**

This stack will install an automatic movie, tv-shows and music content fetcher, using bittorrent protocol. This stacks contains : 

- [Transmission + Openvpn](https://github.com/haugene/docker-transmission-openvpn)
- [Jackett](https://github.com/linuxserver/docker-jackett)
- [Radarr](https://github.com/linuxserver/docker-radarr)
- [Sonarr](https://github.com/linuxserver/docker-sonarr)
- [Lidarr](https://github.com/linuxserver/docker-lidarr)


**Maintenance stack**

This stack will install some maintenance tools, including an incremental backup solution and a docker container automatic updater and a graphic dashboard. This stacks contains : 

- [Watchtower](https://github.com/containrrr/watchtower/)
- [Duplicati](https://github.com/duplicati/duplicati)
- [Node-Exporter](https://github.com/prometheus/node_exporter)
- [Prometheus](https://github.com/prometheus/prometheus)
- [Grafana](https://github.com/grafana/)


**Git stack**

This stack will install a git forge. This stacks contains : 

- [Gitea](https://gitea.io/en-us/)


**DNS stack**

This stack will install a DSN level adblock/malware filter. This stacks contains : 

- [Adguard Home](https://github.com/AdguardTeam/AdGuardHome)



# Prerequisites

- an ARMHF device (tested on an Odroid N2 4Gb)
- [Armbian Buster](https://www.armbian.com/odroid-n2/) installed and running (tested on Armbian Buster - mainline kernel 5.4.y)
- [OpenMediaVault](https://github.com/openmediavault/openmediavault) installed and running (tested on OpenMediaVault 5.4.5-1)
- Docker installed and running (tested on 5:19.03.8~3-0~debian-buster)
- **OMV admin panel configured to a different port than 80**
- SSH access
- Basic handling of a ssh tunnel and some simple unix commands

# Installation guide

1. Using your Terminal of choice (Terminal, Putty, etc), log into your server with an admin priviledged account : ```ssh <your server address>```
2. Install git : ```sudo apt-get install git```
3. Fetch this repository content : ```git clone https://github.com/aaaldo/docker-compose-omv5-armhf.git```
4. Pick a stack to deploy and enter its directory : ```cd <name of the stack>```	
5. Rename and open the .env file : ```mv dotenv .env && nano .env``` and edit its content with your informations
6. Check the local ```README.md``` for additionnal setup required for the stack
7. Deploy the stack : ```sudo docker-compose -f docker-compose.yml up -d```

You can then configure each containers individually. I'd suggest you those youtube channels for more informations and tutorials :
   - [DB Tech](https://www.youtube.com/channel/UCVy16RS5eEDh8anP8j94G2A)
   - [Techno Dad Life](https://www.youtube.com/channel/UCX2Vhc0LIzSS9aMzhGFZ7PA)
  
  
