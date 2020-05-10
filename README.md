# docker-compose-omv5-armhf
A set of docker-compose files to quickly and easily set up docker containers on an ARMHF device. 
This project will configure 2 stacks, the cloud stack and content-fetcher stack.


 The cloud stack will deploy the following images :
 
 - [DuckDNS](https://github.com/linuxserver/docker-duckdns)
 - [Traefik  1.7+ ](https://github.com/containous/traefik)
 - [NextCloud](https://github.com/nextcloud/docker)
 - [Redis](https://github.com/redis)
 - [MariaDB](https://github.com/JSurf/docker-rpi-mariadb)
 - [Calibre-Web](https://github.com/linuxserver/docker-calibre-web)

The content-fetcher stack will deploy the following images : 

- [Transmission + Openvpn](https://github.com/haugene/docker-transmission-openvpn)
- [Jackett](https://github.com/linuxserver/docker-jackett)
- [Radarr](https://github.com/linuxserver/docker-radarr)
- [Sonarr](https://github.com/linuxserver/docker-sonarr)
- [Lidarr](https://github.com/linuxserver/docker-lidarr)

# Prerequisites

- an ARMHF device (tested on an Odroid N2 4Gb)
- [Armbian Buster](https://www.armbian.com/odroid-n2/) installed and running (tested on Armbian Buster - mainline kernel 5.4.y)
- [OpenMediaVault](https://github.com/openmediavault/openmediavault) installed and running (tested on OpenMediaVault 5.4.5-1)
- Docker installed and running (tested on 5:19.03.8~3-0~debian-buster)
- **OMV admin panel configured to a different port than 80**
- SSH access
- Basic knowledge of a ssh tunnel and some basic unix commands

# Installation guide

1. Using your Terminal of choice (Terminal, Putty, etc), log into your server with an admin priviledged account : ```ssh <your server address>```
2. Install git : ```sudo apt-get install git```
3. Fetch this repository content : ```git clone https://github.com/aaaldo/docker-compose-omv5-armhf.git```
4. Go to the ```docker-compose-omv5-armhf/cloud``` directory
5. Rename and open the .env file : ```mv dotenv .env && nano .env``` and edit its content with your informations
6. Deploy the stack : ```docker-compose -f docker-compose.yml up -d```
7. Repeat the step 4, 5 and 6 for the ```docker-compose-omv5-armhf/content-fetcher``` directory
8. You can then configure each containers individually. I'd suggest you those youtube channels for more informations and tutorials :
   - [DB Tech](https://www.youtube.com/channel/UCVy16RS5eEDh8anP8j94G2A)
   - [Techno Dad Life](https://www.youtube.com/channel/UCX2Vhc0LIzSS9aMzhGFZ7PA)
  
  
