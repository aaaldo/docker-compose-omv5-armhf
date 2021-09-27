# Podcast stack Installation tips

Please carefully follow those steps to install the docker without issues :

1. Create a youtube API Key : https://elfsight.com/blog/2016/12/how-to-get-youtube-api-key-tutorial/

2. open and edit the config file ```nano config.toml```

3. copy the config file in your configuration directory ```mv config.toml <PATH TO YOUR CONFIG DIR>/podsync```

4. Rename and open the .env file : ```mv dotenv .env && nano .env``` and edit its content with your informations.

5. Deploy the stack : ```sudo docker-compose -f docker-compose.yml up -d```