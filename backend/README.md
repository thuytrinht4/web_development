# The Backend
Backend refers to server-side development that focuses on databases, scripting and website architecture.
This allows all data and visualizations created locally to be hosted on a website and can be accessed
by others web users through website URL.

In this project, we'll build a backend using Flask. Because Flask is written in Python, we can use any Python library in our backend including pandas and scikit-learn.

In this project, I'll practice the following things:
+ setting up the backend
+ linking the backend and the frontend together
+ deploying the app to a server so that the app is available from a web address

## What is Flask?
[Flask](https://flask.palletsprojects.com/en/2.0.x/). A web framework takes care of all the routing needed to organize a web page so that you don't have to write the code yourself!

When you type "[https://www.google.com/](https://www.google.com/)" into a browser, your computer sends out a request to another computer (ie the server) where the Google website is stored. Then the Google server sends you the files needed to render the website in your browser. The Google computer is called a server because it "serves" you the files that you requested.

The HTTP part of the web address stands for Hypter-text Transfer Protocol. HTTP defines a standard way of sending and receiving messages over the internet.

When you hit enter in your browser, your computer says "get me the files for the web page at [https://www.google.com/](https://www.google.com/)": except that message is sent to the server with the syntax governed by HTTP. Then the server sends out the files via the protocol as well.

There needs to be some software on the server that can interpret these HTTP requests and send out the correct files. That's where a web framework like Flask comes into play. A framework abstracts the code for receiving requests as well as interpreting the requests and sending out the correct files.

## Why Flask?
+ First and foremost, we'll be working with Flask because it is written in Python. We won't need to learn a new programming language.
+ Flask is also a relatively simple framework, so it's good for making a small web app.
+ Because Flask is written in Python, we can use Flask with any other Python library including pandas, numpy and scikit-learn. 

In this project, I'll be deploying a data dashboard and pandas will help get the data ready.

## Flask + Pandas + Plotly
The purpose of this section is to give you an idea of how the final web app works in terms of passing information back and forth between the back end and front end. 
The web template you'll be using at the end of the lesson will already provide the code for sharing information between the back and front ends. 
Our task will be to wrangle data using Pandas and set up the plotly visualizations using Plotly.
Since Flask is written in Python, we can use Pandas and Plotly with Flask code to handle backend task with data.
But it's important to get a sense for how the web app works.

The logic is:
1. Wrangle data in a file (aka Python module). In this case, the file is called wrangling.py. The wrangling.py has a function that returns the clean data.
2. Execute this function in routes.py to get the data in routes.py
3. Pass the data to the front-end (index.html file) using the render_template method.
4. Inside of index.html, you can access the data variable with the squiggly bracket syntax {{ }}

The data set comes from this link at the World Bank's data repository: [link to dataset](https://data.worldbank.org/indicator/SP.RUR.TOTL.ZS?view=chart)


