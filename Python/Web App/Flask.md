is a popular web [[Python#Framework|Framework]] for building web applications in the Python programming language.
[Official Doc](https://flask.palletsprojects.com/)

### Installation 

```bash
pip install Flask
```

### Quickstart

Create a python file with the following content:
```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
```

Then to run it you could add this piece of code in the same file:
``` python
if __name__ == "__main__":  
    app.run(debug=True)
# The debug parameter is for development environments mostly because what it does is that when you change a part of the code re runs the app with the "new" app.
```

### Exporting Variables

#### Windows
```powershell
$env:FLASK_APP = "path/to/file/example.py"
$env:FLASK_DEBUG = "True"
flask run
```

#### Linux
```bash
export FLASK_APP=path/to/file/example.py
export FLASK_DEBUG=True
flask run
```

with this default config then if you go to http://127.0.0.1:5000 you should have a web page running that says "Hello, World!"

### Rendering html files

What if instead of making a web page throw a simple html sentence we want to display a whole html file, to do that first we need to follow a set of rules that flask has.

#### Rules
All our html files have to be created undes the same directory our app is and also inside a <u>templates</u> folder. 
Also all the static files like images, css files, javascript files should go inside the <u>static</u> folder.

First of all we have to import the render_tempalte moduke.
```python
from flask import render_template
```

and in our route function we use it like this:
```python
@app.route("/")
def home():
	return render_template("index.html")
```

### Functionalities 

One of the main functionalities that Flask has is that comes with [[Jinja]] preinstalled. 
So you can pass variables to the templates.

Examples:
```python
@app.route("/")
def home():
	array = ["hi", "this", "is", "a", "functionality"]
	return render_template("index.html", array=array, is_true=True)
```

#### Using redirect
```python
from flask import redirect, url_for, render_template

@app.route("/")
def home():
	return render_template("index.html")

#There are two ways of using redirect
# The first one redirecting the template itself harcoding the file
@app.route("/dosomething")
def do_something():
	# does something
	return redirect("index.html")

# Or calling the function that renders the file
@app.route("/dosomething")
def do_something():
	# does something
	return redirect(url_for("home"))
```

#### Setting a secret key

The secret key is used to sign session cookies for protection against cookie data tampering. 

```python
import os

app.config["SECRET_KEY"] = os.environ.get("SECRET_KEY")
```
