# Python Notes

## March 17, 2023 - 10:07 AM
- **strftime("%d/%m/%Y")** -
*Formats a request from the datetime module and returns the date ("30/05/2023")*

##  March 18, 2023 - 14:54 PM
- **from dateutil.relativedelta import relativedelta** - *A module that allows you to add months or days to a current date from the datetime module. 
eg. six_months = date.now() + relativedelta(months+=6)*
- **import requests** - *A request module to pull data from api endpoints. eg. response = requests.get(url=example, headers=hearders, params=params)*
- **import os** - *Using os.environ to store secret keys and api's. eg. os.environ["example"] = "1234dsf".... secret_api_key = os.environ.get("example")..... print(secret_api_key)...1234dsf*

## March 21, 2023 - 18:10 PM
- **import smtplib** -

        def send_emails(self, emails, message, google_flight_link):
            with smtplib.SMTP(EMAIL_PROVIDER_SMTP_ADDRESS) as connection:
                connection.starttls()
                connection.login(MY_EMAIL, MY_PASSWORD)
                for email in emails:
                    connection.sendmail(
                        from_addr=MY_EMAIL,
                        to_addrs=email,
                        msg=f"Subject:New Low Price Flight!\n\n{message}\n{google_flight_link}".encode('utf-8')
                    )
    Using the smtplib module to send emails from "MY_EMAIL" to someone's email address with flight deals.
    
## March 31, 2023 - 05:25 AM
- **BeautifulSoup** - Is a HTML and XML parser that grabs data from a website target without using an API
- <code>from bs4 import BeautifulSoup</code>
- Sometimes it is necessary to specify the encoding type of the html you are reading. This can be achieved by adding <code>encoding="utf8"</code> after the html target.
- <code>tag.getText()</code> - *will return the text portion of the html code*
- <code>soup.select(selector=".heading")</code> -*will return all the elements within the heading class*
- <code>soup.select_one(selector=".heading")</code> -*will return the first element within the heading class*
- <code>example.index(250)</code> - this is will return the index position of 250 in a list.
- <code>dict(reversed(list(movie_title_dict.items())))</code> -*this is a way of reversing the order of a dictionary by the keys*
## April 08, 2023 - 06:48 AM 
### Selenium
- driver.get(url="www.example.com") -*open a url*
- result = driver.find_element(By.CSS_SELECTOR, "#articlecount a") -*find a specific element within the www.example.com html page.
- view_source = driver.find_element(By.LINK_TEXT, "View source") -*look on a html page for "View source" link*
- view_source.click() -*click onto that element*
## April 16, 2023 - 08:20 AM
- Popular backend development frameworks for python are Flask and Django
- Flask is suited for beginners and Django for commercial or large scale projects
- CLIENT -  SERVER  -  DATABASE

````markdown
Python Decorators Example

    import time
    current_time = time.time()
    print(current_time)

    def speed_calc_decorator(function):
        def wrapper_function():
            start_time = time.time()
            function()
            end_time = time.time()
            print(f"{function.__name__} run speed: {end_time - start_time}s")
        return wrapper_function

    @speed_calc_decorator
    def fast_function():
        for i in range(10000000):
            i * i
            
    @speed_calc_decorator
    def slow_function():
        for i in range(100000000):
            i * i
            
    fast_function()
    slow_function()
 
````
## April 18, 2023 - 05:58 AM
- Setting up a basic Flask website 
````
from flask import Flask

app = Flask(__name__)


@app.route('/')
def home_page():
    return "hello world"


if __name__ == "__main__":
    app.run(debug=True)
    
````
- When setting up a basic Flask file. You need to put all the images and CSS files in a directory called "static" and all the html files in a directory called "templates"

## May 14, 2023 - 10:26 AM
- HTML files must be in a directory called "templates" for it to render
- CSS files and images etc must be under a directory called "static"
- JINJA - templating language built for Python allowing you to use python code. for example if you use {{ 5 * 30 }} the HTML will display 150
- <code> @app.route("/guess/\<name>") </code> - We can capture the user input from the url bar into a variable called "name" using the code above. If you want to capture a number use "\<int:number>"
````
<!doctype html>
<title>Hello from Flask</title>
{% if name %}
  <h1>Hello {{ name }}!</h1>
{% else %}
  <h1>Hello, World!</h1>
{% endif %}
````
- We can use for loops and if statements within the HTML template using the above syntax to start and end the function
- <code> \<a href="{{ url_for('get_blog') }}">Go to Blog\</a> </code> - This is how you can create a hyperlink on the website that routes to another part of the HTML site, In this example you will be redirected to the "Blog" page if there is a defined function called  def get_blog(): You can also pass over a variable using the the following example <code> \<a href="{{ url_for('get_blog', number=3) }}">Go to Blog\</a> </code>

## May 30, 2023 - 09:40 AM

### Creating a virtual enviroment to work in with VSC
- Open terminal with ctrl `
- Type python -m venv .venv
- Then type .\.venv\Scripts\activate 
- You are now working within a virtual enviroment
- You can also use a requirements.txt in the folder you are working in to create a virtual environment

### Example of a for loop and if statement using Jinja2
````
{% if books: %}
        <ul>
        {% for book in books %}
            <li> 
            {{ book["Title"] }} - {{ book["Author"] }} - {{ book["Rating"] }}
            </li>    
        {% endfor %}
        </ul>
    {% else %}
            <p>Library is empty.</p>
    {% endif %}
````

### SQlite Datebase
- SQlite is so popular that it comes preloaded with python installations.
- Use <code>import sqlite3</code> at the top of your project
- Then define the datebase by <code>db = sqlite3.connect("example.db")</code>
- A file called example.db will automatically be created inside the working directory

### Using Flask SQL Alchemy
First we create a new database
````
from flask import Flask
from flask_sqlalchemy import SQLAlchemy
app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = "sqlite:///<name of database>.db"
db = SQLAlchemy(app)
````
Next we create a new table
````
class Book(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    title = db.Column(db.String(250), unique=True, nullable=False)
    author = db.Column(db.String(250), nullable=False)
    rating = db.Column(db.Float, nullable=False
 
db.create_all()
````
Then we can create a new record in that database
````
new_book = Book(id=1, title="Harry Potter", author="J. K. Rowling", rating=9.3)
db.session.add(new_book)
db.session.commit()
````
To read all records we can use
````
all_books = session.query(Book).all()
````
Or read a particular record by query
````
book = Book.query.filter_by(title="Harry Potter").first()
````
If you want to update the particular record by query
````
book_to_update = Book.query.filter_by(title="Harry Potter").first()
book_to_update.title = "Harry Potter and the Chamber of Secrets"
db.session.commit() 
````
Or update a record by the primary key
````
book_id = 1
book_to_update = Book.query.get(book_id)
book_to_update.title = "Harry Potter and the Goblet of Fire"
db.session.commit()
````
and finally to delete a particular record by primary key
````
book_id = 1
book_to_delete = Book.query.get(book_id)
db.session.delete(book_to_delete)
db.session.commit()
````
and delete by particular value
````
book_id = 1
book_to_delete = Book.query.filter_by(title="Harry Potter").first()
db.session.delete(book_to_delete)
db.session.commit()
````
## June 04, 2023 - 09:21 AM

### REST

REST (Representational State Transfer) is an architectural style that defines a set of constraints and principles for designing networked applications, particularly web services, allowing communication between different systems over the internet using standard HTTP methods.

Some other architectural styles are Soap, GraphQL and Falcor. But the gold standard for Web API is REST.

Some HTTP verbs used by REST are:
- GET
- POST
- PUT
- PATCH
- DELETE

### Postman

Postman is a software application that helps developers with creating and testing APIs, allowing for efficient collaboration and simplifying the API development process.

<br></br>
**What is the difference between PUT and PATCH?**
*PUT replaces the entire entry and PATCH modifies or updates part of an existing entry*




