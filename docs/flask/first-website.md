# Flask Beginner Tutorial
Basic Flask concepts and routing tutorial

# Flask Basics
How to create a very simple first webpage

## First install Flask

`pip install flask`

## Import Flask

`from flask import flask`

## Create instance of Flask

`app = Flask(__name__)`

## Route to homepage
`@app.route('/')`

## Define function to display content
`def index():
    return '<h1>Hello Puppy!</h1>'`
    
## Run server
`if __name__ == '__main__':
    app.run()`
<br>
You will get an output that says:
> Running on http://127.0.0.1:5000/
<br>
Click on link to see your first webpage
