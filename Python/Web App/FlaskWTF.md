is a [[Flask]] extension that provides a set of tools for working with web forms in Flask applications. It is built on top of the [WTForms library](https://wtforms.readthedocs.io/), which is a flexible forms validation and rendering library for [[Python]]
[Offical Doc](https://flask-wtf.readthedocs.io/)

### Installation

```bash
pip install -U Flask-WTF
```

### Quickstart

Form creation:
```python
from flask_wtf import FlaskForm
# Fields doc: https://wtforms.readthedocs.io/en/2.3.x/fields/
from wtforms import StringField, SubmitField  
from wtforms.validators import DataRequired  
  
  
class EditForm(FlaskForm):  
    rating = StringField(label="Your Rating", validators=[DataRequired()])  
    review = StringField(label="Your Review", validators=[DataRequired()])  
    submit = SubmitField(label="Done")
```

Calling the form from the route:
```python
@app.route('/submit', methods=['GET', 'POST'])
def submit():
	# Here we create the form object
    form = EditForm()
    # Then if validate do something
    if form.validate_on_submit():
        return redirect('/success')
    # Passing the form as form to the html template
    return render_template('submit.html', form=form)
```

Creating the form inside the [[HTML]]:
```html
<form method="POST" action="/">
    {{ form.csrf_token }}
    {{ form.rating.label }} {{ form.name(size=20) }}
    {{ form.review.label }} {{ form.name(size=20) }}
    <input type="submit" value="Go">
</form>
```

#### Capture data of the form

```python
# Example of a login form this would be defined on a flask route function

if form.validate_on_submit():
	username = form.username.data
	password = form.password.data 
```

The names that we are using <u>form.username.data</u> should match the one in our form definition.