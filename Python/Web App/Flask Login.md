is a popular third-party extension for the [[Flask]] web framework that provides user authentication and session management functionality. It simplifies the process of handling user authentication, managing user sessions, and restricting access to certain pages or resources in the [[Python]] application.
[Official Doc](https://flask-login.readthedocs.io/en/latest/)

### Installation

```bash
pip install flask-login
```

### Quickstart

```python
from flask_login import LoginManager

login_manager = LoginManager()
login_manager.init_app(app)

@login_manager.user_loader  
def load_user(user_id):  
    return User.query.get(int(user_id))
```

To use Flask Login it is important that you have a database with a User table. See [[Flask SQLAlchemy]] to more info.
Also you can use it along [[FlaskWTF]] and [[Flask Bootstrap]] to create the Login/Register forms.
Another important topic is that you should maintain the security of the passwords so you can hash and salt them with [[Werkzeug]]

This are examples of usage of Flask login:
#### Register route

```python
@app.route('/register', methods=["GET", "POST"])  
def register():  
    form = RegisterForm()  
    if form.validate_on_submit():  
  
        if User.query.filter_by(email=form.email.data).first():  
            #User already exists  
            flash("You've already signed up with that email, log in instead!")  
            return redirect(url_for('login'))  
  
        hash_and_salted_password = generate_password_hash(  
            form.password.data,  
            method='pbkdf2:sha256',  
            salt_length=8  
        )  
        new_user = User(  
            email=form.email.data,  
            name=form.name.data,  
            password=hash_and_salted_password,  
        )  
        db.session.add(new_user)  
        db.session.commit()  
        login_user(new_user)  
        return redirect(url_for("home"))  
  
    return render_template("register.html", form=form, current_user=current_user)
```

#### Login route

```python
@app.route('/login', methods=["GET", "POST"])  
def login():  
    form = LoginForm()  
    if form.validate_on_submit():  
        email = form.email.data  
        password = form.password.data  
  
        user = User.query.filter_by(email=email).first()  
        # Email doesn't exist or password incorrect.  
        if not user:  
            flash("That email does not exist, please try again.")  
            return redirect(url_for('login'))  
        elif not check_password_hash(user.password, password):  
            flash('Password incorrect, please try again.')  
            return redirect(url_for('login'))  
        else:  
            login_user(user)  
            return redirect(url_for('get_all_posts'))  
    return render_template("login.html", form=form, current_user=current_user)
```
Here flash is used to show in the web page those messages we also have to add some code to the [[HTML]] file. [Message Flashing](https://flask.palletsprojects.com/en/2.3.x/patterns/flashing/)

#### Logout route

```python
@app.route('/logout')  
def logout():  
    logout_user()  
    return redirect(url_for('home'))
```