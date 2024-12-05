## Setting up the Backend

### Install Dependencies

1. **Python 3.7** - Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

2. **Virtual Environment** - We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organized. Instructions for setting up a virual environment for your platform can be found in the [python docs](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

3. **PIP Dependencies** - Once your virtual environment is setup and running, install the required dependencies by navigating to the `/backend` directory and running:

```bash
pip install -r requirements.txt
```

#### Key Pip Dependencies

- [Flask](http://flask.pocoo.org/) is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) is the Python SQL toolkit and ORM we'll use to handle the lightweight SQL database. You'll primarily work in `app.py`and can reference `models.py`.

- [Flask-CORS](https://flask-cors.readthedocs.io/en/latest/#) is the extension we'll use to handle cross-origin requests from our frontend server.

### Set up the Database

With Postgres running, create a `capstone_db` database:
```bash
createdb capstone_db
```
Populate the database using the `capstone.psql` file provided. From the `backend` folder in terminal run:

```bash
psql capstone_db < capstone.psql
```

### Run the Server

From within the `./backend` directory first ensure you are working using your created virtual environment.

To run the server, execute:

```bash
flask run --reload
```

The `--reload` flag will detect file changes and restart the server automatically.

### RBAC
- Casting assistant permissions:
    "get:actors",
    "get:movies"
- Casting director permissions:
    "delete:actors",
    "get:actors",
    "get:movies",
    "patch:actors",
    "patch:movies",
    "post:actors"
- Executive producer permissions:
    "delete:actors",
    "delete:movies",
    "get:actors",
    "get:movies",
    "patch:actors",
    "patch:movies",
    "post:actors",
    "post:movies"

### TOKEN
- ASSISTANT_TOKEN = 'eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IkgxUmpHTXYyUVRVMEFlcFpIVGppOCJ9.eyJpc3MiOiJodHRwczovL2h1bmducTQ1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NzUwNjMzNDc3NjE1MGM1ZGRjZTExZTAiLCJhdWQiOiJjYXBzdG9uZWFwaXMiLCJpYXQiOjE3MzMzMjc4ODEsImV4cCI6MTczMzMzNTA4MSwic2NvcGUiOiIiLCJhenAiOiJXbVcwakRKdzdyTHZEdDBmZ3lWZlNEc0xWd29tcGZqayIsInBlcm1pc3Npb25zIjpbImdldDphY3RvcnMiLCJnZXQ6bW92aWVzIl19.nBFLC4jC_RYaPSdyjnN3KGVOGpVRQvAg5cSJdsJcbd00KfDIgXhI3vP0ELARrJhBJqxL62KRQa0BbUB5dOAxOtTiL-MY1t-7x-0-hisZS8aF1T8vXbT43J8RLLK7oAbWPz3YbOVXoZGNkC0QUgLBbQLBSgMLRiCuZ2Mxci24Ow6hR2ElDXJVwM9AnaULy-7QjTP6ncFw9rXgCqA43LJ8y1Cro4mfhJ7VDnH3W4_VzTvdMjTnbsolrWyO3CvZP9ii6a-B-c71AYaDGWMqwsFKUI5qtJe08QfJ7tpXA-SjjDZX51ad9aAyOftQHJzKd-6c16In8LSN565RLB_3qiCAXQ'
- DIRECTOR_TOKEN = 'eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IkgxUmpHTXYyUVRVMEFlcFpIVGppOCJ9.eyJpc3MiOiJodHRwczovL2h1bmducTQ1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NzUwNjFlOWVkMzA3ODRmNmNlM2Y4MGIiLCJhdWQiOiJjYXBzdG9uZWFwaXMiLCJpYXQiOjE3MzMzMjc3NjEsImV4cCI6MTczMzMzNDk2MSwic2NvcGUiOiIiLCJhenAiOiJXbVcwakRKdzdyTHZEdDBmZ3lWZlNEc0xWd29tcGZqayIsInBlcm1pc3Npb25zIjpbImRlbGV0ZTphY3RvcnMiLCJnZXQ6YWN0b3JzIiwiZ2V0Om1vdmllcyIsInBhdGNoOmFjdG9ycyIsInBhdGNoOm1vdmllcyIsInBvc3Q6YWN0b3JzIl19.I93XANtSrQHeyjZNHk_Lzqsmw6z4fvGRqI5AwStKTK8TV7eBusSvlVPG3cyQU6y9_bl5gk4vbNx4KXBdThh2bwleOjL2yDlkt8_0GZDrUptffbS6XHX1oxnPhWptSW4Usi1tGzBWko1rt7vC76GS0upy0Sqma7A9Jd5383rWDQQSeOcUCBKJvlx5VH1Vvr7q2Co5ZfiLuYc6i0pTUSpF9NWicq55PHfwtkUDcQSfjtPOqmlzbuYFqLeL7j7BP-rX4YGzrQlnxuh4LFgXUpb6ZFIbh7ICE-pMlENh-FoMu8sAi1y-1zMq0k_mpOoLvdz1uHQSryO-ETZKSzWbXyAzyQ'
- PRODUCER_TOKEN = 'eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IkgxUmpHTXYyUVRVMEFlcFpIVGppOCJ9.eyJpc3MiOiJodHRwczovL2h1bmducTQ1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NzUwNjMwNGM4ODZiMTVkYjhhNDAxOTciLCJhdWQiOiJjYXBzdG9uZWFwaXMiLCJpYXQiOjE3MzMzMjc0MTIsImV4cCI6MTczMzMzNDYxMiwic2NvcGUiOiIiLCJhenAiOiJXbVcwakRKdzdyTHZEdDBmZ3lWZlNEc0xWd29tcGZqayIsInBlcm1pc3Npb25zIjpbImRlbGV0ZTphY3RvcnMiLCJkZWxldGU6bW92aWVzIiwiZ2V0OmFjdG9ycyIsImdldDptb3ZpZXMiLCJwYXRjaDphY3RvcnMiLCJwYXRjaDptb3ZpZXMiLCJwb3N0OmFjdG9ycyIsInBvc3Q6bW92aWVzIl19.KK3K0N9f2adT7sEsz9blHhmz1DGxSNbLFm_nkhABOEFmrqtP_LyqpIHEMXG_X_f58QwZZLZxy4-Xrx50vtzLyRSDtatE2igzwJ-1bHcbji0S7ol74KG3bSGVHJlUmdTA3OEXmk_Je9vyclsOKmQDDzcAzOA1OqOuCEF2zZQ7SRbg6A85PnfU6ljnvefOvcOr5YA-u6CJqa3dh7d9Y35wL0b5h5wZ7bNR9zG-ZvsxIsk9A8vgBLSumTG7VqO-XzO5C6OybGbGcQq8Ao9KsHtExinsSLiwP47ZUhQGNgdrZbkZvv2aRGHtRr6oPpgVBdR7gn56ACTAU_MHqEJkxGNSxw'

### Expected endpoints and behaviors

### `GET '/actors'`
- Fetch the list of all actors from the server. 
- Request Arguments: None
- Returns: A list of actor objects containing the attributes id, bio, gender and name.

```json
{
    "actors": [
        {
            "id": 1,
            "name": "Actor 1",
            "age": 18,
            "gender": "Male",
        },
        {
            "id": 2,
            "name": "Actor 2",
            "age": 19,
            "gender": "Female",
        },
        {
            "id": 3,
            "name": "Actor 3",
            "age": 20,
            "gender": "Male",
        }
    ],
    "success": true
}
```

### `POST '/actors'`
- post a new actor to the server.
- Request Arguments: An object containing string attributes including bio, gender, and name.
```json
        {
            "name": "actor name",  
            "age": 18,
            "gender": "Female",
        }
```
- Returns: An object containing the information of the newly added movie, including id, bio, gender, and name.
```json
{
    "actor": {
        "id": 4,
        "name": "actor name",
        "age": 19,
        "gender": "Male",
    },
    "success": true
}
```

### `PATCH '/actors/<int:actor_id>'`
- Find the actor with the matching ID from the URL and modify that actor's data.
- Request Arguments: An object has at least one of these properties: bio, gender, or name.
```json
        {
            "name": "updated name",  
            "age": 18, 
            "gender": "Male"
        }
```
- Returns: An object containing the information of the newly updated movie, including id, bio, gender, and name.

```json
{
    "actor": {
        "id": 1,
        "name": "updated name",
        "age": 22,
        "gender": "Male",
    },
    "success": true
}
```

### `DELETE '/actors/<int:actor_id>'`
- Find and delete the actor whose ID matches the ID in the URL.
- Request Arguments: None
- Returns: An object with an actor_removed property that holds the ID of the recently deleted actor.

```json
{
    "actor_removed": 1,
    "success": true
}
```

### `GET '/movies'`
- Fetch the list of all movies from the server. 
- Request Arguments: None
- Returns: A list of movie objects containing the attributes id, genre, producer and title.

```json
{
    "movies": [
        {
            "genre": "Genre 1",
            "id": 1,
            "producer": "Producer 1",
            "title": "Movie 1",
            "release_date": "20240505"
        },
        {
            "genre": "Genre 2",
            "id": 2,
            "producer": "Producer 2",
            "title": "Movie 2",
            "release_date": "20240506"
        },
        {
            "genre": "Genre 3",
            "id": 3,
            "producer": "Producer 3",
            "title": "Movie 3",
            "release_date": "20240507"
        }
    ],
    "success": true
}
```

### `POST '/movies'`
- post a new actor to the server.
- Request Arguments: An object containing string attributes including bio, gender, and name.
```json
        {
            "name": "Test Actor",  
            "age": 23,
            "gender": "Female"
        }
```
- Returns: An object containing the information of the newly added movie, including id, bio, gender, and name.
```json
{
    "actor": 
        {
            "id": 4,
            "name": "Test Actor",  
            "age": 23,
            "gender": "Female"
        },
    "success": true
}
```

### `PATCH '/movies/<int:movie_id>'`
- Find the actor with the matching ID from the URL and modify that actor's data.
- Request Arguments: An object has at least one of these properties: bio, gender, or name.
```json
        {
            "name": "updated name",  
            "age": 27,
            "gender": "Male"
        }
```
- Returns: An object containing the information of the newly updated movie, including id, bio, gender, and name.

```json
{
    "actor": 
        {
            "id": 1,
            "name": "updated name",  
            "age": 27,
            "gender": "Male"
        },
    "success": true
}
```

### `DELETE '/movies/<int:movie_id>'`
- Find and delete the actor whose ID matches the ID in the URL.
- Request Arguments: None
- Returns: An object with an actor_removed property that holds the ID of the recently deleted actor.

```json
{
    "actor_removed": 1,
    "success": true
}
```

## Testing

Write at least one test for the success and at least one error behavior of each endpoint using the unittest library.

To deploy the tests, run

```bash
dropdb capstone_db_test
createdb capstone_db_test
psql capstone_db_test < capstone.psql
python test_app.py