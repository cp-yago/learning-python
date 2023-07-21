# Learning Flask

## What is Flask?
Flask is a micro web framework written in Python. It is classified as a microframework because it does not require particular tools or libraries. It has no database abstraction layer, form validation, or any other components where pre-existing third-party libraries provide common functions. However, Flask supports extensions that can add application features as if they were implemented in Flask itself. Extensions exist for object-relational mappers, form validation, upload handling, various open authentication technologies and several common framework related tools. Extensions are updated far more regularly than the core Flask program.

## Fundamentals

## Installation:
Before you can begin, you need to install Flask. You can do this by running the following command in your terminal or command prompt:

```bash
pip install Flask
```

## Creating a Basic Flask Application

Here's an example of a basic Flask application:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return "Hello, World!"

if __name__ == '__main__':
    app.run()
```

In this example, we import the Flask module and create an instance of the Flask class. We define a route using the `@app.route()` decorator, which specifies the URL endpoint ("/") and the function that will handle the request. The function returns the response, in this case, the string "Hello, World!".

## Running the Flask Application:
To run the Flask application, save the file with a `.py` extension (e.g., `app.py`). In your terminal or command prompt, navigate to the directory where the file is located, and run the following command:

```
python app.py
```

The Flask development server will start, and you can access your application in your web browser by visiting `http://localhost:5000`.

## Routing:
Flask allows you to define multiple routes to handle different URLs. Here's an example:

```python
@app.route('/')
def home():
    return "Home Page"

@app.route('/about')
def about():
    return "About Page"
```

In this example, we define two routes: one for the home page ("/") and one for the about page ("/about"). Each route is associated with a function that returns the respective page content.

## HTTP Responses:
Flask provides various ways to construct HTTP responses. Here are a few examples:

```python
from flask import Flask, render_template, jsonify, redirect

@app.route('/')
def index():
    return "Welcome to the index page"

@app.route('/json')
def json_data():
    data = {'name': 'John', 'age': 30}
    return jsonify(data)

@app.route('/redirect')
def redirect_to_home():
    return redirect('/')

@app.route('/html')
def render_html():
    return render_template('index.html')
```

In this example, we use the `return` statement to return different types of responses. The first route returns a plain text response. The second route returns JSON data using the `jsonify()` function. The third route redirects the user to the home page ("/"). The fourth route renders an HTML template using the `render_template()` function.

## Handling HTTP Response Code 
You can set the code by using the `status_code` parameter of the `return` statement or by using the `make_response()` function.

1. Using the `status_code` parameter:
   
   ```python
   from flask import Flask

   app = Flask(__name__)

   @app.route('/')
   def index():
       return "Hello, World!", 200  # Set the response code to 200 (OK)

   @app.route('/error')
   def error():
       return "An error occurred.", 500  # Set the response code to 500 (Internal Server Error)

   if __name__ == '__main__':
       app.run()
   ```

   In this example, we specify the response code as the second value returned by the `index()` and `error()` functions. The response codes `200` and `500` correspond to "OK" and "Internal Server Error", respectively.

2. Using the `make_response()` function:

   ```python
   from flask import Flask, make_response

   app = Flask(__name__)

   @app.route('/')
   def index():
       response = make_response("Hello, World!")
       response.status_code = 200
       return response

   @app.route('/error')
   def error():
       response = make_response("An error occurred.")
       response.status_code = 500
       return response

   if __name__ == '__main__':
       app.run()
   ```

   In this example, we use the `make_response()` function to create a response object. We then set the `status_code` attribute of the response object to the desired HTTP response code.

By setting the appropriate response code, you can convey the status of the HTTP request to the client. Some commonly used response codes include `200` (OK), `201` (Created), `400` (Bad Request), `404` (Not Found), and `500` (Internal Server Error). You can refer to the official HTTP status code documentation for more information on different response codes and their meanings.

## Working with HTTP methods in Flask. 
Here are some code examples to demonstrate how to handle different HTTP methods:

1. Handling GET Requests:
   ```python
   from flask import Flask, request

   app = Flask(__name__)

   @app.route('/', methods=['GET'])
   def get_handler():
       return 'This is a GET request.'

   if __name__ == '__main__':
       app.run()
   ```

   In this example, a route is defined for the root URL (`'/'`) and specifies that it should only handle GET requests. When a GET request is made to the root URL, the `get_handler()` function is executed, and it returns a simple message.

2. Handling POST Requests:
   ```python
   from flask import Flask, request

   app = Flask(__name__)

   @app.route('/', methods=['POST'])
   def post_handler():
       data = request.json  # Get the JSON data sent in the request
       return f'This is a POST request. Data: {data}'

   if __name__ == '__main__':
       app.run()
   ```

   In this example, a route is defined for the root URL (`'/'`) and specifies that it should only handle POST requests. When a POST request is made to the root URL, the `post_handler()` function is executed. It retrieves the JSON data from the request using `request.json` and returns a message with the received data.

3. Handling PUT Requests:
   ```python
   from flask import Flask, request

   app = Flask(__name__)

   @app.route('/', methods=['PUT'])
   def put_handler():
       data = request.json  # Get the JSON data sent in the request
       return f'This is a PUT request. Data: {data}'

   if __name__ == '__main__':
       app.run()
   ```

   In this example, a route is defined for the root URL (`'/'`) and specifies that it should only handle PUT requests. When a PUT request is made to the root URL, the `put_handler()` function is executed. It retrieves the JSON data from the request and returns a message with the received data.

4. Handling DELETE Requests:
   ```python
   from flask import Flask, request

   app = Flask(__name__)

   @app.route('/', methods=['DELETE'])
   def delete_handler():
       return 'This is a DELETE request.'

   if __name__ == '__main__':
       app.run()
   ```

   In this example, a route is defined for the root URL (`'/'`) and specifies that it should only handle DELETE requests. When a DELETE request is made to the root URL, the `delete_handler()` function is executed, and it returns a simple message.

These examples demonstrate how to handle different HTTP methods (GET, POST, PUT, DELETE) in Flask. By defining routes with specific methods, you can create APIs that respond differently based on the HTTP method used in the request.

## Data Manipulation (Databases)
Here's a guide on how to connect to a database, perform CRUD (Create, Read, Update, Delete) operations, and use Object-Relational Mappers (ORMs) like SQLAlchemy. Let's dive into code examples:

1. Connecting to a Database:
To connect to a database in Flask, you can use SQLAlchemy, which is a popular ORM. First, you'll need to install SQLAlchemy using a package manager like pip. Then, you can create a database connection by configuring the database URI.

```python
from flask import Flask
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///mydatabase.db'
db = SQLAlchemy(app)
```

In this example, we create a Flask application and configure the SQLite database URI. You can replace it with the URI for your specific database. The `db` object represents the database connection.

2. Defining a Model:
Next, you'll define a model class that represents a table in the database. Each attribute in the class corresponds to a column in the table.

```python
class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(50), nullable=False)
    email = db.Column(db.String(100), unique=True)

    def __repr__(self):
        return f'<User {self.name}>'
```

In this example, we define a `User` model with `id`, `name`, and `email` attributes. The `__repr__` method specifies how the model should be represented when printed.

3. Performing CRUD Operations:
You can now perform CRUD operations on the database using SQLAlchemy methods.

- Create (Insert) Operation:
To insert a new record into the database, create an instance of the model and add it to the session.

```python
new_user = User(name='John Doe', email='john@example.com')
db.session.add(new_user)
db.session.commit()
```

- Read (Query) Operation:
To retrieve data from the database, use SQLAlchemy's query methods.

```python
all_users = User.query.all()  # Retrieve all users

user = User.query.get(1)  # Retrieve a user by ID

filtered_users = User.query.filter_by(name='John Doe').all()  # Retrieve users based on a condition
```

- Update Operation:
To update an existing record, modify the attributes of the model and commit the changes.

```python
user = User.query.get(1)
user.email = 'john.doe@example.com'
db.session.commit()
```

- Delete Operation:
To delete a record, retrieve it from the database and delete it from the session.

```python
user = User.query.get(1)
db.session.delete(user)
db.session.commit()
```

These examples demonstrate how to perform CRUD operations using SQLAlchemy in Flask APIs. Remember to import the necessary modules and configure the database connection before using these code snippets. SQLAlchemy provides a powerful and flexible way to work with databases in Flask applications.


## Validation and authentication in Flask APIs. 
Here's a guide with code examples:

### Validation:
When working with APIs, it's important to validate the data sent by clients to ensure it meets the expected criteria. Flask provides various ways to validate data, including using libraries like `Flask-WTForms` or implementing custom validation logic.

Example using `Flask-WTForms`:
1. Install `Flask-WTForms` using pip: `pip install Flask-WTForms`.

```python
from flask import Flask, request, jsonify
from flask_wtf import FlaskForm
from wtforms import StringField, IntegerField
from wtforms.validators import DataRequired, Length

app = Flask(__name__)
app.config['SECRET_KEY'] = 'your_secret_key'


class MyForm(FlaskForm):
    name = StringField('Name', validators=[DataRequired(), Length(min=2, max=50)])
    age = IntegerField('Age', validators=[DataRequired()])


@app.route('/api/user', methods=['POST'])
def create_user():
    form = MyForm(request.form)
    if form.validate():
        # Process the validated data
        name = form.name.data
        age = form.age.data
        # Code to create user or perform other operations
        return jsonify({'message': 'User created successfully'})
    else:
        # Invalid data, return error response
        return jsonify({'errors': form.errors}), 400


if __name__ == '__main__':
    app.run()
```

In this example, `Flask-WTForms` is used to define a form called `MyForm` with fields `name` and `age`. Validators are applied to each field to ensure they are not empty and meet specific criteria. When the `/api/user` endpoint is called with a POST request, the form is validated, and if valid, the user creation process can proceed. Otherwise, an error response is returned with the validation errors.

### Authentication:
Authentication is crucial to ensure the security of your API by verifying the identity of the clients making requests. There are different authentication methods you can use in Flask, such as token-based authentication or integrating with third-party authentication providers.

Example using token-based authentication with Flask-JWT:
1. Install `Flask-JWT` using pip: `pip install Flask-JWT`.

```python
from flask import Flask, request, jsonify
from flask_jwt import JWT, jwt_required, current_identity

app = Flask(__name__)
app.config['SECRET_KEY'] = 'your_secret_key'
app.config['JWT_AUTH_URL_RULE'] = '/api/auth'
app.config['JWT_EXPIRATION_DELTA'] = timedelta(hours=1)

# Sample user data
users = [
    {'id': 1, 'username': 'john', 'password': 'password123'},
    {'id': 2, 'username': 'jane', 'password': 'secret'}
]


class User(object):
    def __init__(self, id):
        self.id = id
        self.username = users[id - 1]['username']
        self.password = users[id - 1]['password']

    def __str__(self):
        return f"User(id='{self.id}', username='{self.username}')"


def authenticate(username, password):
    for user in users:
        if user['username'] == username and user['password'] == password:
            return User(user['id'])
    return None


def identity(payload):
    user_id = payload['identity']
    return User(user_id)


jwt = JWT(app, authenticate, identity)


@app.route('/api/protected')
@jwt_required()
def protected_resource():
    return jsonify({'message': f'Hello, {current_identity.username}! This is a protected resource.'})


if __name__ == '__main__':
    app.run()
```

In this example, `Flask-JWT` is used to implement token-based authentication. The `authenticate()` function checks the provided username and password against the sample user data. If valid, a JWT token is generated, and the `identity()` function retrieves the user object associated with the token. The `/api/protected` endpoint is protected with the `jwt_required()` decorator, ensuring only authenticated users can access it.

These examples provide a starting point for validation and authentication in Flask APIs. You can further customize and enhance these approaches based on your specific requirements.