# DevOps-Challenge
This repo contains the source code used as part of the interview assessment for Platform (DevOps) Engineer role.

The application code itself has been sourced from https://github.com/laravel/laravel

This task should take a couple hours to complete

User Story :

As Platform (DevOps) Engineer, you received a task to design and create Infrastructure as code (IaC) to deploy containerized application in Public Could (AWS, Azure, etc) provider

The Developer Team has decided to use PHP Laravel framework as the major programming language, hence you are required to set-up a web server to server the application services. The team has provided you a repo with the application code, as well as a Dockerfile and Docker Compose file

Requirement :

1. Provision Public Cloud resoures
a. The application should be reachable over the internet on port 80
b. Compute should not be accessible by public
c. Able to ssh to compute for temporary

2. Kindly include in README file
a. Step to provision the infrastructure
b. Step to build the and deploy the application
c. Any details changes you performed to the provided source code

3. Send us your code with documentation as tarball

Take a note, we will attempt to provision infrastructure and application you provided in our Cloud environment for evaluation

Tips
1. Use your own free Cloud account to make sure the application is working
2. Dont need to keep the project running as part of submission

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
