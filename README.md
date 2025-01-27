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

## Question 3

SELECT 
    SUM(CASE WHEN trip_distance <= 1 THEN 1 ELSE 0 END) AS "Up to 1 mile",
    SUM(CASE WHEN trip_distance > 1 AND trip_distance <= 3 THEN 1 ELSE 0 END) AS "1 to 3 miles",
    SUM(CASE WHEN trip_distance > 3 AND trip_distance <= 7 THEN 1 ELSE 0 END) AS "3 to 7 miles",
    SUM(CASE WHEN trip_distance > 7 AND trip_distance <= 10 THEN 1 ELSE 0 END) AS "7 to 10 miles",
    SUM(CASE WHEN trip_distance > 10 THEN 1 ELSE 0 END) AS "Over 10 miles"
FROM 
    green_tripdata
WHERE 
    lpep_pickup_datetime >= '2019-10-01' 
    AND lpep_pickup_datetime < '2019-11-01';

## Question 4

SELECT 
    DATE(lpep_pickup_datetime) AS "pickup_day",
    MAX(trip_distance) AS "longest_trip_distance"
FROM 
    green_tripdata
GROUP BY 
    DATE(lpep_pickup_datetime)
ORDER BY 
    longest_trip_distance DESC
LIMIT 1;

