#cXML Punchout

##Purpose of app
To provide API access to a supplier's catalog which is compatible with the customer's ERP system, such that it can be viewed, searched and ordered from within the customer's ERP system

##Key features
####Web pages

- User Registration
- User Login
- User Profile

####API

- User Registration
- User Login
- User Profile
- Authenticate
- Search For Product
- Place Order
- Reset Login credentials

###User Registration

- User visits a dedicated website (eg, api.yourdomain.co.uk/register) to set up their account
- They enter a username, email and password into a given form.
- This sends a JSON formatted API post to the server including the username, email and password, which will be encrypted using bcrypt
- This username, email and encrypted password are stored in a Customers table in a mongodb database, along with a unique API key, and their currently authorised access, which is just to login at this point
- The user is then redirected to a login page (eg, api.yourdomain.co.uk/login).
- The administrator of the API is sent an email that requests authorisation to use the API
- Whatever authorisation the administrator grants will be added to the customer entry in the Customers table

###Login

- They enter their username/email and password ito a login page (eg, api.yourdomain.co.uk/login)
- This sends a JSON formatted API post to the server a including the username/email and password, which will be encrypted using bcrypt
- If the user has provided a correct username/email address and a correct password, the next page shows their API key, and other information specific to them.

###Profile

- Allows user maintenance of username and password, as well as requesting a new API key.

###Search For Product
