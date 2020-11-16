# Web stack Installation tips

1. Using your Terminal of choice (Terminal, Putty, etc), log into your server with an admin priviledged account : ```ssh <your server address>```
2. Copy the config.json file in your configuration folder : ```mv config.json <YOUR DATA DIRECTORY>/NginxProxyManager``` and edit its content with your informations
3. Deploy the stack : ```docker-compose -f docker-compose.yml up -d```
  
  
