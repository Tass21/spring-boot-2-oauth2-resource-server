# Spring Boot 2 Oauth2 resource server example

This is a bare-bones Spring Boot 2 Oauth2 resource server with an authorization server.
I put this here, cause there was no good example out there on how to do it. 

This is a bootstrap project for all the startups out there who have trouble hiring talent and have to do with low paid students, who crawl stackoverflow all day to hack something together. Do it properly and save a bunch of money!

## Running

Here's a way to run it with a docker mysql server (highly recommended for developing/testing).
If you wish to run it against your native mysql environment, then just change the `application.properties` file or define your own profile `application-[your-profile].properties`.

Docker way:
1. Install docker
2. Run the docker container in the root of the project `docker-compose up`
3. Create a new terminal tab and cd into `bash_scripts` folder, run `./create-tables-add-data.sh` (This will setup all the oauth DB tables)
4. Install dependencies `mvn clean install`
5. Run it `mvn spring-boot:run`

Server should now be up and running on `http://localhost:8080`.

## Get an access token with Postman

1. Install Postman
2. Import Postman collection from the `project.postman_collection.json` file
3. Run the `/oauth/token` POST request and get a access_token.
4. Change the token value to the access_token in the other requests and you should get 200 OK responses.

## Database

It is what it is, mysql 5.7. But it can easily be switched out for Postgres or whatever you need.
