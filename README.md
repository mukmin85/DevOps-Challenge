# DevOps-Challenge
This repo contains the source code used as part of the interview assessment for Platform (DevOps) Engineer role.

The application code itself has been sourced from https://github.com/laravel/laravel

For more information about the content about the challenge itself, please reach out to your hiring manager.

## Requirement to success

Environment = WSL2 + Docker Desktop

Tools = git, curl, terraform (if using cloud), docker, docker-compose

## Step-Step

root@xnb135-wsl:/home# git clone https://github.com/mukmin85/DevOps-Challenge.git

root@xnb135-wsl:/home# cd DevOps-Challenge

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose up --build -d

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose images

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose ps
