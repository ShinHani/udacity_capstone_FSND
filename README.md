### Project Motivation: Casting Agency System  

**1. Problem Identification**  
The traditional process of managing movie projects and assigning actors involves numerous manual tasks, leading to inefficiencies, communication gaps, and delays. Keeping track of movie details, actor information, and role assignments can be cumbersome, especially when scaling up to manage multiple productions simultaneously.  

**2. Opportunity Exploration**  
With advancements in technology, there is a significant opportunity to develop a centralized, streamlined system to manage these processes efficiently. Automating the workflows for casting, actor management, and movie production can reduce errors, save time, and improve collaboration between roles such as Casting Assistants, Casting Directors, and Executive Producers.

**3. Goals and Objectives**  
The primary goal of this project is to build a **Casting Agency System** that allows for the efficient management of movies and actors. The system will provide the following key functionalities:  
- **Movies:** Create, update, view, and delete movie records.  
- **Actors:** Manage actor profiles, including adding, updating, viewing, and removing actors from the system.  
- **Role-Based Access Control (RBAC):** Ensure that users have appropriate permissions based on their roles (Casting Assistant, Casting Director, Executive Producer).  

**4. Benefits and Impact**  
- **Efficiency:** Automates repetitive tasks such as data entry and retrieval, significantly reducing the time spent on administrative tasks.  
- **Collaboration:** Facilitates better communication and workflow between different roles in the company.  
- **Scalability:** Enables the agency to manage an increasing number of movies and actors without additional overhead.  
- **Accuracy:** Minimizes human error through standardized processes and clear role permissions.  
- **Security:** Ensures sensitive data is only accessible to users with appropriate permissions, safeguarding company assets.

**5. Personal/Team Motivation**  
As the **Executive Producer**, you are passionate about leveraging technology to simplify complex workflows. This system aligns with your vision of creating a cutting-edge production environment, ensuring that your team can focus more on creative tasks rather than administrative ones. By implementing this system, you aim to lead your company into a new era of digital efficiency and productivity.  

**6. Implementation Strategy**  
- **Endpoints:** RESTful API endpoints for managing movies and actors.  
- **Role Definitions:** Implement RBAC to ensure each user role has the appropriate level of access and capabilities.  
- **Testing:** Comprehensive tests to verify both successful and error-prone behavior of endpoints, as well as ensure proper RBAC enforcement.  

This project will serve as a foundation for a scalable and efficient casting management system, ultimately helping the company achieve its production goals more effectively.

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
- ASSISTANT_TOKEN = 'eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IkgxUmpHTXYyUVRVMEFlcFpIVGppOCJ9.eyJpc3MiOiJodHRwczovL2h1bmducTQ1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NzUwNjMzNDc3NjE1MGM1ZGRjZTExZTAiLCJhdWQiOiJjYXBzdG9uZWFwaXMiLCJpYXQiOjE3MzMzNjg0OTAsImV4cCI6MTczMzM3NTY5MCwic2NvcGUiOiIiLCJhenAiOiJXbVcwakRKdzdyTHZEdDBmZ3lWZlNEc0xWd29tcGZqayIsInBlcm1pc3Npb25zIjpbImdldDphY3RvcnMiLCJnZXQ6bW92aWVzIl19.ah52kH4IY2IGPh0bRyMZaLTRaKLEJJib7J_MW0YY1wFbh3t6n-YZVOUekHYi-0930dMFr9Y_0wzeEExKcEj_Vz92Xj-1mb8aZbm9PDl1MTPW-tgpNCU_4KgyI-NIGk5ZsFjR-42pvZLWTL3t2QE3dmOlrgFS7YfW4oSRdcIUrQvEIFgLVfEXA5BtvP53op133YUVCpEGz5CctazBdqQciyDjcLYCA1KJAq5bajxozaZNopCLd985efbylWh8bcjir4AbfhgqfVXA4o1wag6aLo2dVrmDEgvApuH7NqQWTX5CaXy5gaCpi2Azd0CBlwEPS9eDPs_tqetK0x28ZnZ3Uw'
- DIRECTOR_TOKEN = 'eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IkgxUmpHTXYyUVRVMEFlcFpIVGppOCJ9.eyJpc3MiOiJodHRwczovL2h1bmducTQ1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NzUwNjFlOWVkMzA3ODRmNmNlM2Y4MGIiLCJhdWQiOiJjYXBzdG9uZWFwaXMiLCJpYXQiOjE3MzMzNjg0MTIsImV4cCI6MTczMzM3NTYxMiwic2NvcGUiOiIiLCJhenAiOiJXbVcwakRKdzdyTHZEdDBmZ3lWZlNEc0xWd29tcGZqayIsInBlcm1pc3Npb25zIjpbImRlbGV0ZTphY3RvcnMiLCJnZXQ6YWN0b3JzIiwiZ2V0Om1vdmllcyIsInBhdGNoOmFjdG9ycyIsInBhdGNoOm1vdmllcyIsInBvc3Q6YWN0b3JzIl19.ey-gcoh7FdFfC-NxHE3Hs1Zr8Aul7X3SF48hAVbhZ1-YIjPdp3SESMbwbgJq8ZwZduEFJHziskpgXaej9YaFkk1vNsBqDlmx3YrgTGAbl0ScDsEElK6nfzBZD1X0i1RBX8P7BkyhDWeHgsa8QVs3O_FlSoZlVZ1d_XWe4_ZVlGEcwTu40l8eMKFloErwzqNWB4i6xY6qWx7UChc35qW31FlozJ8CSEW4gLJidC-vWjTvZyxMgOpvWW5S6yBJE0Ne0M-n_pLxpYoTNPgdauZHXfK24UKDlM82D_26FmuzIey53buubF1V7PD9op1MYSr2pH2F3yCihlZJvCuXKRhAyA'
- PRODUCER_TOKEN = 'eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IkgxUmpHTXYyUVRVMEFlcFpIVGppOCJ9.eyJpc3MiOiJodHRwczovL2h1bmducTQ1LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJhdXRoMHw2NzUwNjMwNGM4ODZiMTVkYjhhNDAxOTciLCJhdWQiOiJjYXBzdG9uZWFwaXMiLCJpYXQiOjE3MzMzNjgyNDAsImV4cCI6MTczMzM3NTQ0MCwic2NvcGUiOiIiLCJhenAiOiJXbVcwakRKdzdyTHZEdDBmZ3lWZlNEc0xWd29tcGZqayIsInBlcm1pc3Npb25zIjpbImRlbGV0ZTphY3RvcnMiLCJkZWxldGU6bW92aWVzIiwiZ2V0OmFjdG9ycyIsImdldDptb3ZpZXMiLCJwYXRjaDphY3RvcnMiLCJwYXRjaDptb3ZpZXMiLCJwb3N0OmFjdG9ycyIsInBvc3Q6bW92aWVzIl19.bn0w0F2ljx0pjIMGnp4hXViqd0OaFAjdYlENO7kUOLyAXyzZdg75Uy5krL2600boM7VOuytlDA1TtZCMpwyVqNsq4w3TB0xbiBvrRY0QZ-z9mYfdcCUiLPoCRXzfVersnSLoyXG_uQjsRcwTW7dVPEFUTYHTCYdVui-GuLuUBiaFEdA0IUt_z9ty93KvrtnDfJ88qQpAat6WoRy575invGd3G91DSQyTMmYewKsAdJY6zoXaSxVJXWpaRGLIczRpdxoavFZS7M9vV-WWbEO93hKSVhTxH5kwR_cKRoLwIHZke_TAPUH9Lx9nJ90a3sK4ef_a216mjAjoMHlndipBnA'

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
            "name": "Actor1",  
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
            "name": "Actor1",  
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
```
##  Hosting instructions - Render
On the New Postgres page:
    Step 1: Enter a name for the new database service: postgres-deployment-example
    Step 2: Select an instance type: Free
    Step 3: Click Create Database button
On the New Web Service page:
   Step 1: Provide a name for the new database service: render-deployment-example
   Step 2: Select an instance type: Free
   Step 3: Enter the build command: pip install -r requirements.txt
   Step 4: From the Postgres service (name: "postgres-deployment-example"), click the "Info" side navigation and copy the Internal Database URL from the Connections page.
   Step 5: Create an environment variable with the key: DATABASE_URL and Database URL value copied from the Postgres service.
   Add a second Environment variable with the key EXCITED and value true.


After the Web Service is ready, you can open your Flask app on the browser by clicking the app URL under the title on the Web Service page.
## Endpoints
https://render-deployment-example-udacity-jbhn.onrender.com