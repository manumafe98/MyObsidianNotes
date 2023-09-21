is an extension of [[Flask]], which provides a high-level Object-Relational Mapping (ORM) interface for working with relational databases. It allows developers to interact with databases using [[Python]] code, without the need for writing complex SQL queries.
[Official Doc](https://flask-sqlalchemy.palletsprojects.com/)

### Installation

```bash
pip install -U Flask-SQLAlchemy
```

### Quickstart

```python
# Importing the module
from flask_sqlalchemy import SQLAlchemy

# Creating our db object
db = SQLAlchemy()

# configure the SQLite database, relative to the app instance folder
app.config["SQLALCHEMY_DATABASE_URI"] = "sqlite:///project.db"

# initialize the app with the extension
db.init_app(app)
```

Here in the app.config we are creating our db <u>project.db</u> normally it is created under the instance folder. Normally this sqlite databases are used to development environments and Postgresql or another mysql orm for production. So we can configure it like this.

```python
import os

app.config["SQLALCHEMY_DATABASE_URI"] = os.environ.get("DATABASE_URL", "sqlite:///project.db")
```
In this way our app will prioritize the [[Flask#Exporting Variables|Exported variable]] and if its not found or not working will use the local db.

### Define a model

This is the definition our table will take.
```python
class Movies(db.Model):  
    id = db.Column(db.Integer, primary_key=True)  
    title = db.Column(db.String(250), unique=True, nullable=False)  
    year = db.Column(db.Integer, nullable=False)  
    description = db.Column(db.Text, nullable=False)  
    rating = db.Column(db.Float, nullable=False)  
    ranking = db.Column(db.Integer, nullable=False)  
    review = db.Column(db.String(250), unique=True, nullable=False)  
    img_url = db.Column(db.String(250), unique=True, nullable=False)
```

Then we have two alternatives create the table within the code with:
```python
with app.app_context():
    db.create_all()
```

or in the terminal:
```bash
flask shell
db.create_all()
```

### CRUD

is an acronym that stands for Create, Read, Update, and Delete. It refers to the four basic functions that are commonly used in database applications and other data management systems.

#### Read all records
```python
all_movies = db.session.query(Movies).all()
```

#### Add a new record
```python
new_movie = Movies(title="The lion king",
				 year=1994,
				 description="A young lion prince...",
				 rating=9.0,
				 ranking=3,
				 review="A great and emotional movie!",
				 img_url="https://image.example")

db.session.add(new_movie)
db.session.commit()
```

#### Read a particular record by query
```python
movie = Movies.query.filter_by(title="Harry Potter").first()
```

#### Update a particular record by query
```python
movie_to_update = Movies.query.filter_by(title="Harry Potter").first()
movie_to_update.title = "Harry Potter and the Chamber of Secrets"
db.session.commit()
```

#### Update a record by PRIMARY KEY
```python
movie_id = 1
movie_to_update = db.session.get(Movies, movie_id)
movie_to_update.title = "Harry Potter and the Goblet of Fire"
db.session.commit()
```

#### Delete a particular record by PRIMARY KEY
```python
movie_id = 1
movie_to_delete = db.session.get(Movies, movie_id)
db.session.delete(movie_to_delete)
db.session.commit()
```
