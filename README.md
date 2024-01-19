# Documentation - UbbNetwork

This documentation strives to explain how this project works, and what it does.

## Overview
UbbNet is a social network, that allows people to create posts about what they are thinking.
They can view each other's profiles and posts, leave a like, and can create friendships.

## Deployment
Currently, a development deployment is set up at [https://dev.teamhex.laurcons.ro](https://dev.teamhex.laurcons.ro). Go check it out.

## Tech stack
This is a web application, built on top of Spring, with an Angular frontend.

The backend is your typical Spring installation. It uses Hibernate to connect to a database. Due to this, the backend is database-agnostic, but on the development deployment is uses MySQL.

The frontend uses Angular, and its UI is built on top of Angular Material.

## Running the backend locally
The backend, hosted at [/team-hex-cs-pc/ubbnet-spring](https://github.com/team-hex-cs-pc/ubbnet-spring), is just a IntelliJ IDEA project and should be able to be opened directly.

Make sure you have configured a link to a database. Populate the `src/main/resources/application-dev.properties` file with connection info.

## Deploying the backend
* Make sure you have Maven installed. Check your version with `mvn -v`.
* Change your directory to the root of the project.
* Run `mvn install`.
* Make sure the `./mvnw` file has execution permissions on your user.
* Run `./mvnw spring-boot:run`.
* Your application should now start.

Make sure you have configured a link to a database. Populate the `src/main/resources/application-dev.properties` file with connection info.

You can change the port the app runs on by setting the `PORT` environment variable.

Our deployments use a reverse proxy to handle requests. The Spring app is NOT directly exposed to the Internet.

## Running the frontend locally
The frontend, hosted at [/team-hex-cs-pc/ubbnet-angular](https://github.com/team-hex-cs-pc/ubbnet-angular), can be opened in your favorite JavaScript dev environment.

Install all dependencies using `npm install`, then run the app locally using `ng serve`.

The `ng` command is part of the Angular CLI. Install it with `npm i -g @angular/cli`.

Make sure the config in `src/environments/environment.ts` points to the correct API URL.

## Deploying the frontend
* Make sure you have node version >18 and npm installed.
* Run `npm install`.
* Run `npm run build -- --configuration=[env]`.
* Your application is now built at `./dist` and can be statically served.

Our deployments use Nginx to statically serve the `dist` directory.

Make sure the config in `src/environments/environment-[env].ts` points to the correct API URL.