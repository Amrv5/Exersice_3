# demo app - developing with Docker :

## This demo app shows a simple user profile app set up using

   ** index.html with pure js and css styles .
   ** nodejs backend with express mode.
   ** mongodb for data storage .

 **All components are docker-based

## To start the application

### Step 1: start mongodb and mongo-express

 docker-compose -f docker-compose.yaml up

 **You can access the mongo-express under localhost:8080 from your browser

### Step 2: in mongo-express UI - create a new database "my-db"

### Step 3: start node server

 node server.js


**You can access the application under localhost:3000 from your browser

 To build a docker image from the application

 docker build -t my-app:1.0 
 
-----------------------------------------------------------------------------------

#Docker File code :
-------------------------------

FROM node:13-alpine

ENV MONGO_DB_USERNAME=admin \
    MONGO_DB_PWD=password

RUN mkdir -p /home/app

COPY . /home/app

CMD ["node", "/home/app/server.js"]

