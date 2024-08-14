# Full stack docker example

## Setup
1. docker-compose up --build
2. docker exec -it backend-docker sh <!-- Enter backend docker container -->
3. NODE_ENV=docker node_modules/.bin/sequelize db:create
4. NODE_ENV=docker node_modules/.bin/sequelize db:migrate
5. NODE_ENV=docker node_modules/.bin/sequelize db:seed:all

## Intro
This repo contains an example of dockerizing a full stack application. Please have a look at my [blog](https://medium.com/@siddharth.lakhara/dockerizing-a-full-stack-js-app-ceb99411996e) if you want to know how to create it

## Tech stack
 - Frontend - ReactJs
 - Backend - HapiJs
 - DB - Postgres

 
Network Configuration: Using links is deprecated in favor of Docker's built-in network capabilities. By default, Docker Compose will create a network that all services are connected to, allowing them to communicate with each other by service name 


want to persist the database data, you should mount a volume for the db service. Without this, all data will be lost when the container is restarted.
 Ensure that your backend service can connect to the database. You may need to pass environment variables such as DB_HOST, DB_PORT, DB_USER, DB_PASSWORD, and DB_NAME to the backend service

Key Points:
Directory Structure:

Frontend: Typically listens on port 3000 (as per your docker-compose.yml).
Backend: Typically listens on port 8080 (as per your docker-compose.yml).
Working Directory:

Both Dockerfiles use /usr/src/app as the working directory, which is a common convention.
EXPOSE:

The frontend exposes port 3000, and the backend exposes port 8080, aligning with the services in your docker-compose.yml


Tons of error, cannot help