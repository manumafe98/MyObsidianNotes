is a [[Flask]] extension that provides a set of templates and tools built with [[Bootstrap]], a popular front-end framework for developing responsive, mobile-first websites into [[Python]] code. 
This is possible because flask comes with [[Jinja]] for templating.
[Official Doc](https://pythonhosted.org/Flask-Bootstrap/)

### Installation

```bash
pip install Flask-Bootstrap
```

### Quickstart

In the pythn code:
```python
from flask import Flask
from flask_bootstrap import Bootstrap

def create_app():
  app = Flask(__name__)
  Bootstrap(app)

  return app
```

Basic [[HTML]] example file:
```html
<!-- Using the base bootstrap template -->
{% extends "bootstrap/base.html" %}

{% block title %}This is an example page{% endblock %}

{% block content %}
  <h1>Hello, Bootstrap</h1>
{% endblock %}
```

We can also add styling like this:
```html
<!-- Style block -->
{% block styles %}  
  {{ super() }}  
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Nunito+Sans:300,400,700">  
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Poppins:300,400,700">  
  <link rel="stylesheet" href="{{ url_for('static', filename='css/styles.css') }}">  
{% endblock %}
```

### Creating forms

You can also create [[FlaskWTF]] forms like this:

```html
{% extends 'bootstrap/base.html' %}  
{% import "bootstrap/wtf.html" as wtf %}

{% block content %}  
<div class="content">  
    <h1 class="heading">Add a Movie</h1>  
    <form class="form" method="post" role="form">  
        {{ wtf.quick_form(form) }}  
    </form>  
</div>  
{% endblock %}
```

If you leve the quick_form like that depending the browser the user has it will come with the default validation, but there are browsers that dont have so we can define it like this to remove it:
```html
{{ wtf.quick_form(form, novalidate=True) }}
```

To create a button you have to use it like this:
```html
{{ wtf.quick_form(form, novalidate=True, button_map={"submit": "primary"}) }}
```

The <u>primary</u> refers to this [Bootstrap btn doc](https://getbootstrap.com/docs/4.0/components/buttons/) basically defines the styling of the button.