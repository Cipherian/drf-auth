# Things_api

- Author: Daniel Brott

- Date: 1/19/2023

- Updated 1/21/2023

  - Added authentication

  - Switched to python 3.10-slim

  - Now uses authentication to verify users who an modify or look at specific objects

- Updated 1/25/2023

  - Added jwt authentication

  - Switched to gunicorn in yml


## Config and Startup

- Create virtual environment and install the dependencies

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

## HTTP request
- First you need to make a post request to the api token endpoint with username and password credentials
with ```docker run webserver python3 manage.py createsuperuser```, then run the following command to
retrieve a token.

  - http POST :8000/api/token/ username=user password=password

  -Then use that token with the following command, which will bring up the main detail list web page

  - http POST :8000/ "Authorization: Bearer insert token" 

- If you have created a specific item for a user you can make the following
http GET request in order to view the specific item. Make sure to fill in the correct
username and password. You will also need to create an item if you wish to use the GET command on it.

- http GET :8000/1/ username=user password=password

- This should retrieve an object that looks like this:

```EX:
{
    "created_at": "2023-01-26T03:08:45.583965Z",
    "description": "eee",
    "id": 1,
    "name": "Biscotti",
    "owner": 1,
    "updated_at": "2023-01-26T03:08:45.583982Z"
}
```



