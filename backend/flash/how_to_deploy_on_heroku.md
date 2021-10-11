# Instructions Deploying to Heroku
[Heroku](https://devcenter.heroku.com/articles/heroku-cli#standalone-installation) is a Cloud Application Platform that support hosting websites on their server. 
With a small webapp like this project, it offers free hosting without expiration.

Here is the steps to get the web app running with Heroku:

1. Create a new folder webapp, and move all of the application folders and files to the new folder
2. Create a virtual environment (if not yet created) and then activate the environment
3. The new environment will automatically come with Python packages meant for data science. In addition, pip install the specific Python packages needed for the web app:


    pip install flask==0.12.5 pandas==0.23.3 plotly==2.0.15 gunicorn==19.10.0


4. Install the Heroku command-line tools in Linux or MacOS. For Windows, download zip file for installation from the [official installation instructions](https://devcenter.heroku.com/articles/heroku-cli#standalone-installation)

    curl https://cli-assets.heroku.com/install-ubuntu.sh | sh

5. Log into heroku with the following command. Heroku asks for your account email address and password, which you type into the terminal and press enter.


    heroku login -i


6. The next steps involves some housekeeping:
   + remove `app.run()` from worldbank.py
   + type `cd webapp` into the Terminal so that you are inside the folder with your web app code.

   Create a proc file, which tells Heroku what to do when starting your web app:


    touch Procfile


   Then open the Procfile and type:

    web gunicorn worldbank:app

7. Create a ***requirements.txt*** file, which lists all of the Python packages that your app depends on:


    pip freeze > requirements.txt


8. Initialize a git repository and make a commit:


    # Run it just once, in the beginning
    git init
    # For the first time commit, you need to configure the git username and email:
    git config --global user.email "you@example.com"
    git config --global user.name "Your Name"


   Whenever you make any changes to your `webapp` folder contents, you will have to run `git add` and `git commit` commands.

    
    # Every time you make any edits to any file in the web_app folder
    git add .
    # Check which files are ready to be committed
    git status
    git commit -m "your message"

9. Now, create a Heroku app:


    heroku create my-app-name --buildpack heroku/python
    # For example, 
    # heroku create sudkul-web-app --buildpack heroku/python
    # The output will be like:
    # https://sudkul-web-app.herokuapp.com/ | https://git.heroku.com/sudkul-web-app.git

   where my-app-name is a unique name that nobody else on Heroku has already used. 
   You can optionally define the build environment using the option `--buildpack heroku/python` 
   The `heroku create` command should create a git repository on Heroku and a web address for accessing your web app. 
   You can check that a remote repository was added to your git repository with the following terminal command:
   
    git remote -v

10. Before you finally push your local git repository to the remote Heroku repository, you will need the following 
environment variables (kind of secrets) to send along:


    # Set any environment variable to pass along with the push
    heroku config:set SLUGIFY_USES_TEXT_UNIDECODE=yes
    heroku config:set AIRFLOW_GPL_UNIDECODE=yes
    # Verify the variables
    heroku config

   If your code uses any confidential variable value, you can use this approach to send those values secretly. 
   These values will not be visible to the public users. Now, push your local repo to the remote Heroku repo:

    # Syntax
    # git push <remote branch name> <local branch name>
    git push heroku master

   Other useful commands are:

    # Clear the build cache
    heroku plugins:install heroku-builds
    heroku builds:cache:purge -a <app-name> --confirm <app-name>
    # Permanently delete the app
    heroku apps:destroy  <app-name> --confirm <app-name>

Now, you can type your web app's address, such as https://thuytrinh-webapp.herokuapp.com/, in the browser to see the results.

# Other Services Besides Heroku
Heroku is just one option of many for deploying a web app, and Heroku is actually owned by [Salesforce.com](https://www.salesforce.com/ap/?ir=1).

The big internet companies offer similar services like [Amazon's Lightsail](https://aws.amazon.com/lightsail/),
[Microsoft's Azure](https://docs.microsoft.com/en-us/samples/azure-samples/python-docs-hello-world/python-flask-sample-for-azure-app-service-linux/), 
[Google Cloud](https://cloud.google.com/appengine/docs/standard/python/setting-up-environment), 
and [IBM Cloud (formerly IBM Bluemix)](https://www.ibm.com/cloud/blog). 
However, these services tend to require more configuration. Most of these also come with either a free tier 
or a limited free tier that expires after a certain amount of time.

# Database for Your App
The web app in this lesson does not need a database. All of the data is stored in CSV files; 
however, it is possible to include a database as part of a Flask app. One common use case would be to store user login 
information such as username and password.

Flask is database agnostic meaning Flask can work with a number of different database types. If you are interested in 
learning about how to include a database as part of a Flask app, here are some resources:

+ [Flask Mega Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-iv-database)
+ [Heroku - Provision a Database](https://devcenter.heroku.com/articles/getting-started-with-python#provision-a-database)
