## Dynamic Routing

Route to different page depending on situation, such as in when different users log in to different accounts.
However, steps to create and initialize Flask app remain the same.

## Create app.route


`@app.route('/some_page/<name>')
def other_page(name): #essentially we're just returning user and formatting the name into the user
    return 'User: {}'.format(name)`

**<name>** is an input, in this case for example the username. Flask will route to a different page depending on username input.
    

## Run server
`if __name__ == "__main__":
    app.run()`
    
Must add /some_page/<name> to the end of the URL, where name can be anything
