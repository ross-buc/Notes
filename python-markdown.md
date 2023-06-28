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


## June 08, 2023 - 08:41 AM

### **Pandas**
Pandas is a powerful open-source Python library that provides data manipulation and analysis tools, offering easy-to-use data structures and data analysis functionalities for handling structured data efficiently. It allows users to manipulate, filter, and analyze data in various formats, making it a popular choice for data scientists and analysts.

``` python
import pandas as pd

# Read the CSV file into a Pandas DataFrame
data = pd.read_csv('data.csv')

# Display the first few rows of the DataFrame
print(data.head())

# Calculate the mean value of a specific column
mean_value = data['column_name'].mean()
print("Mean:", mean_value)

# Filter the DataFrame based on a condition
filtered_data = data[data['column_name'] > 10]

# Save the filtered data to a new CSV file
filtered_data.to_csv('filtered_data.csv', index=False)
```
````
data = data.head()
````
The data.head() function is used to display the first few rows of a DataFrame or Series. It is a convenient way to quickly inspect the data and get a glimpse of its structure.

By default, data.head() displays the first 5 rows of the DataFrame or Series. However, you can specify the number of rows to display by passing an integer argument to the head() function. For example, data.head(10) will display the first 10 rows.

````
data.shape()
````
In pandas, the data.shape attribute is used to determine the shape or dimensions of a DataFrame or Series. It returns a tuple containing the number of rows and columns in the data structure.

For example, if you have a DataFrame called data, you can access its shape by using data.shape. The result will be a tuple in the format (rows, columns).
````
data.columns()
````
In pandas, the data.columns attribute is used to access the column labels or names of a DataFrame. It returns an Index object containing the column names.

For example, if you have a DataFrame called data, you can access its column names by using data.columns. The result will be an Index object that represents the column labels.


````
data.isna()
````
The data.isna() function is used to identify missing or NaN (Not a Number) values in a DataFrame or Series. It returns a boolean DataFrame or Series of the same shape as the input, where each element is True if it corresponds to a missing value and False otherwise.

````
data.dropna()
````
The data.dropna() function is used to remove or drop missing values from a DataFrame or Series. It returns a new DataFrame or Series with the missing values removed.
````
rows_with_na = df[df.isna().any(axis=1)]
````
This will return each row that is missing data in one or all of the columns for that row.
````
rows_with_na = df[df.isna().any(axis=0)]
````
This will return each column that is missing data in one or all of the columns. You dont have to specify the axis=0 as it is 0 by default
````
{df_btc_price.isna().values.any()}
````
This will return a True or False statement if there are any NA values in the DF
````
{df_btc_price.isna().values.sum()}
````
This will return the sum of all NA values in the DF
````
df_data.isna().sum(axis=0)
````
This will return a list of all the columns and how many NA values are in each column.
````
df_na_entries = df_data[df_data.isna().any(axis=1)]
````
Will create a new df with all the entries that had a NA value
````
df_apps_clean.duplicated().values.sum()
````
Will give you the total amount of duplicates in the df_apps_clean DF
````
duplicated_rows = df_apps_clean[df_apps_clean.duplicated()]
````
Searching for duplicated entries and creating a DF from the results
````
duplicated_rows[duplicated_rows["App"] == 'Instagram']
````
Searching the duplicated_rows DF for the keyword "Instragram" under column "App"
````
df_apps_clean.drop_duplicates(subset=['App', 'Type', 'Price'])
````
The standard drop_duplicates function will only drop the record if every column entry is identical. We can negate this by specifying "subset" in this example and requiring the app, type and price to be identical for the entry to be dropped.
````
clean_df['Starting Median Salary']
````
In the clean_df it will return the column with the heading "Starting Median Salary". You can use .max() at the end if you want to return the highest value in that column.
````
filtered_theme = themes_df[themes_df['name'] == 'Star Wars']
````
Under the column called 'name' we can create a df with only entries that are 'Star Wars'
````
sets_df[sets_df['theme_id'].isin([18, 158, 209, 261])].count()
````
Using the isin method we can specify multiple theme_ids to look for. Then it will count them up
````
clean_df['Starting Median Salary'].idxmax()
````
This will return the row number with the max value in Starting Median Salary
````
clean_df['Undergraduate Major'].loc[43]
````
Will return the value in column Undergraduate Major @ row 43
````
clean_df.loc(43)
````
This will return all the column headings and values for row 43
````
df['name'].unique()
````
Will return a df with a list of unique (no two the same) in the "name" column
````
df['name'].nunique()
````
Will return a the number of unique items in the "name" column
````
df['name'].value_counts()
````
Will return a df with a list of unique (no two the same) in the "names" and how many times they appear in the df.
````
df_apps.sample(4)
````
we can grab a random sample of 4 rows using this code 
````
clean_df['Undergraduate Major'].loc[clean_df['Starting Median Salary'].idxmin()]
````
You can nest code inside the "loc" method instead of writing two lines of code

Creating a new column
````
new_col = clean_df['Mid-Career 90th Percentile Salary'].subtract(clean_df['Mid-Career 10th Percentile Salary'])
````
Adding the new column to an existing DF
````
clean_df.insert(1, "New", new_col)
````
The first arg being the column location starting at 0, the second arg being the name of the new column and the third arg being the variable to import into the DF
````
df_apps.drop('Last_Updated', axis=1, inplace=True)
````
Deleting the entire column called "Last_Updated" in the same DF using the inplace=True
````
sorted = clean_df.sort_values("New")
````
This will create a new DF under the name sorted and sort the whole DF by the values in "New" from smallest to largest.
````
sorted_by_largest = clean_df.sort_values("New", ascending=False)
````
By adding the ascending=False arg the DF will be sorted by the largest value to the lowest value.
````
clean_df.groupby('Group').count()
````
Using the groupby method and count() we can return the DF grouped together by a defined column label
````
clean_df.groupby("Group")['Starting Median Salary'].mean()
````
Finding the mean value of the starting median salary column and grouped by the "Group" column.
````
df_apps_clean.sort_values(['Rating', 'Reviews'], ascending=[False, False])
````
sorting values by specifying two columns will provide a more accurate answer when it comes to the highest rated and reviewed app
````
pd.options.display.float_format = '{:,.2f}'.format
````
Set the pandas display format so that numbers have two decimal places for example 43.25 instead of 43.2534323

````
pivoted_df = test_df.pivot(index='Age', columns='Actor', values='Power')
pivoted_df
````
You can re-arrange the columns and rows by using the .pivot() method. In the example above we are specifying the index, columns and values
````
filtered_df = df[df['DATE'] == 2020]
````
filtering the database to return all results from 2020
````
filtered_df = df[(df['DATE'].dt.year >= 2012) & (df['DATE'].dt.year <= 2020)]
````
filtering the database to return all results from 2012 to 2020
````
tag_counts = filtered_df.groupby('TAG')['POSTS'].sum()
````
Grouping all the "TAG"s together and summing up their total "POSTS"
````
tag_counts.idxmax()
````
Now that we have a list of the sum of all posts per tag we can simply use idxmax() to return the TAG with the most amount of POSTS
````
sets_df.loc[sets_df['year'] == 2019, 'num_parts'].count()
````
Counting the amount of "num_parts" for the year 2019
````
sets_by_year_df = sets_df.groupby("year").count()
sets_df = sets_by_year_df[:-2]
````
This code shows a DF grouped by the column "year" and then counted. For example if there was 10 entries with the year 1953 then it would show (1953 - 10). Then we can use the slice method to remove the last two entries of the DF using [:-2]
````
new_clean_df[['App', 'Installs']].groupby('Installs').count()
````
Creating a result of two columns App and Installs then grouping the results by how many apps are at each amount of installs
````
filtered_df = sets_df[sets_df['year'] == 1954]
filtered_df.groupby('year')['num_parts'].mean()
````
The DF is filtered to only show results in the year 1954. Then we have found the average amount of "num_parts" in the year 1954
````
themes_by_year.rename(columns = {'theme_id': 'nr_themes'}, inplace=True)

new_df = themes_by_year.rename(columns={'theme_id': 'nr_themes'}, inplace=False)
````
This is a way of renaming the column called 'theme_id' to 'nr_themes. Using inplace=True will allow you to modify the original df. If you use rename=False you will have to assign it to a new DF
````
set_theme_count = pd.DataFrame({'id': set_theme_count.index, 'set_count': set_theme_count.values})
````
We can rename a df without index and value column names by using pd.DataFrame and then using a dict to set the values. Make sure to use a capital F in DataFrame
````
data.info()
````
Will give a good summary of the DF
````
data.describe()
````
Gives a good summary or mins, maxs, and percentile
````
pd.DataFrame(df_tesla).dtypes
````
Using dtypes is a way of finding out what data types are present in each column in the DF. Object = "apple", "banana" etc. int64 = 1,2,3,4 etc and float64 = 12.56, 23.54, 44.22 etc
````
pd.DataFrame(df_tesla).dtypes
````
Using dtypes is a way of finding out what data types are present in each column in the DF. Object = "apple", "banana" etc. int64 = 1,2,3,4 etc and float64 = 12.56, 23.54, 44.22 etc
````
df.DATE = pd.to_datetime(df.DATE)
````
To convert a date or month column into a datetime object we can use the pd.to_datetime function to convert the entries into datetime objects
````
df_btc_price.set_index('DATE', inplace=True)
````
Using the set_index function we can define the index 
````
df_btc_monthly = df_btc_price.resample('M', on='DATE').mean()
````
We can use the .resample function change a datetime object originally set in days to months using the above code. We can also change the value to .last() if you want to make the value equal the last price for that month or max(), min() etc. You can also set the rule to 'Y' for year, 'T' for minute 'D' for day. Checkout more [here](https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#dateoffset-objects)
``` python
data_clean['Decade_Release'] = data_clean['Realease_Date'].dt.year // 10 * 10
```
An example of converting a date into a decade format using floor division and datetime
``` python
df['Install'] = df['Install'].str.replace(',', '')
```
Removing unwanted characters in a column so we can convert it to a int or float dtype
``` python
df["Install"] = df["Install"].astype(float)
```
Will convert the Install column from an object type to a float type
``` python
new_clean_df = new_clean_df[new_clean_df['Price'] <= 250.00]
```
filtering the df to only have Prices that are equal to or less that 250
``` python
new_clean_df.insert(10, "Revenue_Estimate", new_clean_df['Price'] * new_clean_df['Installs'])
```
Creating a new column called Revenue_Estimate and the value being the Price multiplied by the Install and returned into the Revenue_Estimate column
``` python
subset = data.query('USD_Worldwide_Gross > 0 and USD_Domestic_Gross == 0')
```
Using .query we can create a subset of the dataframe quickly using the code example above
<br></br>

### **Anaconda**
Anaconda is a popular open-source distribution for Python and R programming languages, providing a comprehensive platform for data science and machine learning. It includes a collection of pre-installed packages and tools, simplifying the setup and management of environments, making it a convenient choice for data scientists and researchers.

``` python
# Create a new conda environment
conda create -n myenv python=3.9

# Activate the environment
conda activate myenv

# Install a package using conda
conda install pandas

# Install additional packages using pip
pip install numpy matplotlib

# Create a Python script (example.py) that utilizes the installed packages
# example.py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

data = pd.read_csv('data.csv')
# Perform data analysis or visualization using pandas, numpy, and matplotlib

# Deactivate the environment
conda deactivate
```

Then you need to install jupyter by entering in the following:
``` python
conda install jupyter
```
and to launch type "jupyter notebook" into the terminal

<br></br>

## **Matplotlib**

Firstly in the terminal 
``` python
conda install matplotlib
```
then at the top of the file
````
import matplotlib.pyplot as plt
````
Below is a basic setup of a graph using matplotlib
``` python
plt.figure(figsize=(16,10))
plt.xlabel("Date", fontsize=14)
plt.ylabel("Number of Posts", fontsize=14)
plt.ylim(0, 35000)
plt.plot(piv_df.index, piv_df['python'])
```
We can plot multiple sets of data on the same graph simply by adding another plt.plot:
``` python
plt.figure(figsize=(16,10))
plt.xlabel("Date", fontsize=14)
plt.ylabel("Number of Posts", fontsize=14)
plt.ylim(0, 35000)
plt.plot(piv_df.index, piv_df['python'])
plt.plot(piv_df.index, piv_df['java'])
```
or if you have multiple data sets we can use a for loop 
``` python
plt.figure(figsize=(16,10))
plt.xlabel("Date", fontsize=14)
plt.ylabel("Number of Posts", fontsize=14)
plt.ylim(0, 35000)

for column in piv_df.columns:
    plt.plot(piv_df.index, piv_df[column])
```
we can add a legend to the graph to help identify the different plots. Also we can change the properties of the line
``` python
plt.figure(figsize=(16,10))
plt.xlabel("Date", fontsize=14)
plt.ylabel("Number of Posts", fontsize=14)
plt.ylim(0, 35000)

for column in piv_df.columns:
    plt.plot(piv_df.index, piv_df[column], linewidth=3, label=piv_df[column].name)
plt.legend(fontsize=16)    
```
using a method calling "rolling" we can smooth out the data and specify the window and the avg using the below code
``` python
pivv_df = piv_df.rolling(window=6).mean()

plt.figure(figsize=(16,10))
plt.xlabel("Date", fontsize=14)
plt.ylabel("Number of Posts", fontsize=14)
plt.ylim(0, 35000)

for column in pivv_df.columns:
    plt.plot(pivv_df.index, pivv_df[column], linewidth=3, label=pivv_df[column].name)
plt.legend(fontsize=16)
```
A few points from the example below
  - Using the ax1.twinx() method is a way of plotting two data sets on the y axis to compare
  - linewidth to set the thickness of the line on the graph
  - linestyle to set it to dotted
  - set_xlim and set_ylim to set the x and y axis value starting points
  - ax1.grid to overlay a light gray grid onto the graph
  ``` python
  plt.figure(figsize=(14,8), dpi=200)
ax1 = plt.gca()
ax2 = ax1.twinx()
plt.title('UE Benefits Search vs UE Rate 2004-20')
plt.xticks(fontsize=14, rotation=45)
ax1.plot(ue_df['MONTH'], ue_df['UNRATE'], color='#FF0000', linewidth=2.5, linestyle='--')
ax2.plot(ue_df['MONTH'], ue_df['UE_BENEFITS_WEB_SEARCH'], color='b', linewidth=2.5, linestyle='--')

# Set the minimum and maximum values on the axes
ax1.set_ylim([0, 15000])
ax1.set_xlim([ue_df['MONTH'].min(), ue_df['MONTH'].max()])

ax1.set_ylabel('FRED U/E Rate', color='#FF0000')
ax2.set_ylabel('Monthly Search of "Unemployment Benefits"', color='blue')

ax1.xaxis.set_major_locator(years)
ax1.xaxis.set_major_formatter(years_fmt)
ax1.xaxis.set_minor_locator(months)
ax1.grid(color='grey', linestyle='--')
plt.show()
```
Data visualisation with Plotly
````
import plotly.express as px
````
If you are inside a jupyter notebook and you want to pip install use this
````
!pip install plotly
````
first create a pie chart with
````
fig = px.pie(labels=ratings.index, values=ratings.values)
fig.show()
````
And to adjust the title, names, positions etc
``` python
fig = px.pie(labels=ratings.index, 
             values=ratings.values,
            title="Content Rating",
            names=ratings.index)
fig.update_traces(textposition='outside',
                 textinfo='percent+label')
fig.show()
```
to make the pie chart a donut chart add the hole argument
``` python
fig = px.pie(labels=ratings.index, 
             values=ratings.values,
            title="Content Rating",
            names=ratings.index,
            hole=0.6)
fig.update_traces(textposition='outside',
                 textinfo='percent+label')
fig.show()
```
Bar chart easy setup
````
bar = px.bar(x=top_10_cat.index, y=top_10_cat.values)
bar.show()
````
Bar chart set to horizontal with labelling
``` python
h_bar = px.bar(x = category_installs.Installs,
                y = category_installs.index,
                orientation='h',
                title='Category Popularity')
    
h_bar.update_layout(xaxis_title='Number of Downloads', yaxis_title='Category')
h_bar.show()
```

## **NumPy**

NumPy is a Python library that’s used in almost every field of science and engineering. It’s practically THE standard for working with numerical data in Python.

``` python
a = np.arange(10, 30)

array([10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29])
```
We can use np.arange to create an array using a starting value and ending value
``` python
a[-3:]
array([27, 28, 29])

a[3:6]
array([13, 14, 15])

a[12:]
array([22, 23, 24, 25, 26, 27, 28, 29])

a[::2]
array([10, 12, 14, 16, 18, 20, 22, 24, 26, 28])

a[::-1]
array([29, 28, 27, 26, 25, 24, 23, 22, 21, 20, 19, 18, 17, 16, 15, 14, 13, 12, 11, 10])
```
Using python list slicing we can return the array with specific starting and ending aswell as reversing a list of numbers

