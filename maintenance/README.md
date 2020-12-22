# Maintenance stack Installation tips

Please carefully follow those steps to install the docker without issues :

1. Using your Terminal of choice (Terminal, Putty, etc), log into your server with an admin priviledged account : ```ssh <your server address>```

2. Go to your configuration folder (set using the ${CONFIG_PATH} in .env). If not present, create a Prometheus folder : ```mkdir Prometheus```

3. Complete the prometheus configuration file : ```nano prometheus.yml```

4. Copy the prometheus configuration file in the configuration folder : ```cp prometheus.yml ${CONFIG_PATH}/Prometheus```

5. Change permissions on the configuration file : ```sudo chmod 755 ${CONFIG_PATH}/Prometheus/prometheus.yml```

6. Come back to the ```docker-compose-omv5-armhf/maintenance``` folder, and deploy the stack : ```sudo docker-compose -f docker-compose.yml up -d```