# Things_api

- Author: Daniel Brott

- Date: 1/19/2023

- Updated 1/21/2023

  - Added authentication

  - Switched to python 3.10-slim

  - Now uses authentication to verify users who an modify or look at specific objects


## Config and Startup

- python manage.py runserver to run locally
_
- In order to run docker for the first time use: docker-compose up --build -d

- For any subsequent running of the docker container run: docker-compose up -d

- Alternatively you can first run: docker volume create postgres-data

- Then run docker compose up


## Functionality

- Uses Django rest framework to make a CRUD application with JSON

- Uses Docker to create a docker container to run the django rest framework in

## Authentication

- Validates users access to modifying the json objects




