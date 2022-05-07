# cscie88-final-project
CSCIE88 Final Project - Materialized Views from an event sourced data stream. 


# Setup

Pre-requisites: 
- Docker desktop/cli and docker-compose.
- To rebuild images a dockerhub account.
- Also if you are rebuilding the images, you will also need the pack cli installed https://buildpacks.io/docs/tools/pack/
- To run the streaming client you will need to obtain an api key at the MBTA website here ... https://api-v3.mbta.com/ The key is free and is usually issued that same day.

Scripts

- if rebuilding the images, edit the create-images.sh script in the scripts directory; changing the dockerhub repository name to your dockerhub account name. Also edit the docker-compose.yml file in the docker directory and update the 2 image names to your repository
```
docker tag mbtakafkaconsumer:latest barrymullan/mbtakafkaconsumer:latest
```
becomes
```
docker tag mbtakafkaconsumer:latest <your-dockerhub-account>/mbtakafkaconsumer:latest
```
- from your project directory run the script *create-volumes.sh* This will create the docker volume directories (under the docker/final-project directory) that zookeeper, kafka and filebeat data is written to.
```
./scripts/create-volumes.sh
```

Running the services

- from a shell run the following commands
```
cd docker
export MBTA_API_KEY=<your-api-key-from-step-above>
docker-compose up -d
```
You should see something like this ...
![This is an image](https://raw.githubusercontent.com/bmullan-pivotal/cscie88-final-project/main/doc/docker-compose.jpg)







