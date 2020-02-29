# Udagram REST API

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:
1. this backend user.
2. [The Simple Frontend](https://github.com/claudioacioli/udacity-frontend)
A basic Ionic client web application which consumes the RestAPI Backend. 
3. [The Feed RestAPI Backend](https://github.com/claudioacioli/udacity-restapi-feed) a backend feed microservice to show us the content of feeds.
 


***
## Getting Setup

### Installing project dependencies

This project uses NPM to manage software dependencies. NPM Relies on the package.json file located in the root of this repository. After cloning, open your terminal and run:
```bash
npm install
```
>_tip_: **npm i** is shorthand for **npm install**

***

## Running the Server Locally
To run the server locally in developer mode, open terminal and run:
```bash
npm run dev
```

Developer mode runs off the TypeScript source. Any saves will reset the server and run the latest version of the codebase. 

***

## Running the server Locally on Docker

To run this on Docker, open terminal and run:

```bash
docker run --rm --publish 8080:8080 -v $HOME/.aws:/root/.aws --env POSTGRESS_HOST=$POSTGRESS_HOST --env POSTGRESS_USERNAME=$POSTGRESS_USERNAME --env POSTGRESS_PASSWORD=$POSTGRESS_PASSWORD --env POSTGRESS_DB=$POSTGRESS_DB --env AWS_REGION=$AWS_REGION --env AWS_PROFILE=$AWS_PROFILE --env AWS_BUCKET=$AWS_BUCKET --env JWT_SECRET=$JWT_SECRET --name user claudioacioli/udacity-restapi-user
```

***

## Running the server Locally on Minikube

To run this on Minikube, first start Minikube:

```bash
minikube start
```

Then, apply the deployment file:
```bash
kubectl apply -f deployment.yaml
```

Apply the service file:
```bash
kubectl apply -f service.yaml
```

Expose to run:
```bash
kubectl port-forward service/backend-user 8080:8080
```
