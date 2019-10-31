## How Flask works
When we open a browser we see a few things:
Front-End
- **HTML** displays the page elements like the actual text on the website
- **CSS** styles the elemtns liek change font or sizeof the text
- **Bootstrap** provides some automatic styling through CSS and Javascript

Every website will perform some main ops:
- Accept info from user
- Retrieve info from databse
- Create/Update/Delee info in the database
- Display information back to the user

To connect the front-end stuff to web database, we need a web framework.
Web framework's job is to accept user information from website and connect to back-end database and report something relevant that can be stored in the db and communicate it to the front-end so user can see it.

**Flask** is a web framework. Allows to connect Python code to the web. Flask does has reputation for being not scalable. 

## Accepting user information
- Could be something like accepting query into Google search - instance of user filling out info. WTForms is a library that works well with flask
- Communicate with database and retrieve information. In this case its SQLite. SQLite can scale to quite a large website.
- SQLAlchemy allows us to write Python code instead of SQL queries
- Flask is like connector between front-end and back-end info that is stored
- **Jinja** templates grab info from Python and Flask ad send info back as HTML
- Flask renders HTML templates

## Virtual Environment

Launched web app and want to use external python library, but the library gets updated. We can set up virtual environment to help manage dependencies. 
