# DevOps-Challenge
This repo contains the source code used as part of the interview assessment for DevOps Engineer role.

The application code itself has been sourced from https://github.com/laravel/laravel

This task should take a couple hours to complete

User Story :

As DevOps Engineer, you received a task to deploy containerized application on premise

The Developer Team has decided to use PHP Laravel framework as the major programming language, hence you are required to set-up a web server to server the application services. The team has provided you a repo with the application code, as well as a Dockerfile and Docker Compose file

Requirement :

1. Provision a VM 

a. The application should be reachable on port 80

2. Kindly provide screenshot file

a. Step to build the and deploy the application

b. Any details changes you performed to the provided source code

3. Send us your updated file changes as zip file 

Take a note, we will attempt to provision application you provided in our environment for evaluation

## Requirement to success

Tools = git, curl, terraform, docker, docker-compose

## Step-Step

root@xnb135-wsl:/home# git clone https://github.com/mukmin85/DevOps-Challenge.git

root@xnb135-wsl:/home# cd DevOps-Challenge

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose up --build -d

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose images

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose ps

root@xnb135-wsl:/home/DevOps-Challenge# curl localhost:443

root@xnb135-wsl:/home/DevOps-Challenge# curl localhost

Access from Browser http://localhost/
