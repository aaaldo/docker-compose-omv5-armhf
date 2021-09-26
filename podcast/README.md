# Podcast stack Installation tips

Please carefully follow those steps to install the docker without issues :

1. Log on https://developers.google.com/youtube/registering_an_application

2. Create a new project using the select project dropdown

3. Go on the Identifier tab and click the "Create an identifier" button on top. Fill the needed informations and copy the newly created identifier key.

4. open and edit the config file ```nano config.toml```

5. copy the config file in your configuration directory ```mv config.toml <PATH TO YOUR CONFIG DIR>/podsync```

5. Rename and open the .env file : ```mv dotenv .env && nano .env``` and edit its content with your informations.

9. Deploy the stack : ```sudo docker-compose -f docker-compose.yml up -d```