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


    