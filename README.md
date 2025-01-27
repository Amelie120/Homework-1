## Homework1: Docker & SQL

## Question 1
## How I did it
1. I opened my docker desktop to make sure it was running 
2. Checked that docker was working with: 
    docker run hello-world
3. Ran the python image with the it for interactive bash shell with:
    docker run -it python:3.12.8 bash
4. Then I checked the version of pip with:
    pip --version

I did it on windows command propmt and ran all those commands

## Question 2
For this question, the service name for postgres is db and the port that pgAdmin should use is 5432 because in the docker-compose.yaml code you gave us, 5432 is the container port which is where postgres is running and 5433 port is the host port where it is for external acces so we would use 5432.