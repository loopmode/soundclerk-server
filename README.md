# soundclerk

Symfony/Docker API experiment: An app to manage sound files.

## Setup

Make sure you have docker installed.
Then, run `docker-compose up` in the project root.

### Init database

Run `docker ps` to get the CONTAINER ID of the container with the soundclerk/server image.

With that ID, initialize the database:

    docker exec -it YOUR_CONTAINER_ID php bin/console doctrine:database:create
    
Then, initialize the schema:

    docker exec -it YOUR_CONTAINER_ID php bin/console doctrine:schema:create
    
### Add Google Cloud Platform credentials

Log in with your Google account and visit https://console.cloud.google.com/apis/credentials/serviceaccountkey
Create a new service account and save the JSON file as `assets/soundclerk.gcp.json`.
