# Filter stack Installation tips

Please carefully follow those steps to install the docker without issues :

1. Log on the admin panel of OMV, go to the Network section and  Interfaces tab. Select the eth0 interface, and set its IPv4 adress resolving to Static method.

2. Using your Terminal of choice (Terminal, Putty, etc), log into your server with an admin priviledged account : ```ssh <your server address>```

3. Stop the systemd DNS resolver : ```sudo systemctl stop systemd-resolved```

4. Modify the systemd/resolved.conf : ```sudo nano /etc/systemd/resolved.conf``` like follows : 
• Uncomment the **DNS line** and set __127.0.0.1__ as DNS
• Uncomment the **DNSStubListener** line and set its value to **no**

5. Make a copy of the actually used resolv.conf : ```sudo mv /etc/resolv.conf /etc/resolv.conf.bk```

6. Point the modified resolv.conf to the actual resolv.conf with a symlink : ```sudo ln -s /run/systemd/resolve/resolv.conf /etc/resolv.conf```

7. Restart the system DSN resolver : ```sudo systemctl reload-or-restart systemd-resolved```

8. Rename and open the .env file : ```mv dotenv .env && nano .env``` and edit its content with your informations.

9. Deploy the stack : ```sudo docker-compose -f docker-compose.yml up -d```

10. Configure your local machine or your router to use ```<your server address>`` as your main DNS resolver.