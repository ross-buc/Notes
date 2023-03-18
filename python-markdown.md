# Python Notes

## March 17, 2023 - 10:07 AM
- **strftime("%d/%m/%Y")** -
*Formats a request from the datetime module and returns the date ("30/05/2023")*

##  March 18, 2023 - 14:54 PM
- **from dateutil.relativedelta import relativedelta** - *A module that allows you to add months or days to a current date from the datetime module. 
eg. six_months = date.now() + relativedelta(months+=6)*
- **import requests** - *A request module to pull data from api endpoints. eg. response = requests.get(url=example, headers=hearders, params=params)*
- **import os** - *Using os.environ to store secret keys and api's. eg. os.environ["example"] = "1234dsf".... secret_api_key = os.environ.get("example")..... print(secret_api_key)...1234dsf*
