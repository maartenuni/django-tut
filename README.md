# django-tut
Personal invesigation of django

## Getting your project running

- Run a modern version of python e.g. 3.8+ and install django-4.0 in
  a virtual environment.
- Create a new project with a name "mysite" in this example:  
    ```shell
    $django-admin startproject mysite
    ```  
  Subsitute mysite with a name of your liking.
  It will create a new directory with the chosen name and a subdirectory with the chozen name. If the  you want the project to be written in a folder of your own you can use e.g.  
    ```shell
    $django-admin startproject mysite .
    ```  
  This will create the project in your current folder. The project will contain a mysite folder and a
  manage.py file. This first contains settings for your website, the latter is a script to interact with your django project
- In order to start a webserver run e.g. ```python manage.py runserver```. Ignore the migration related warnings for now. Add a portnumber to the arguments in order to run it on a separate port. The server is now running for development, the **runserver** command is not suitable for production.

## Start a django app for your website.
- In the root folder run the following command, this creates the polls app, ofcourse you can specify a name of your own.  
   ```shell
   $python mangage.py startapp polls
   ```  
  This command will create a new directory with the name that you chose for your app.
- add an `urls.py` to the polls folder and `include()` it in `mysite/url.py`.

## Edit the settings for the website
- You can set the backend for the SQL engine (SQLlite) is the default. The settings file is `mysite/settings.py`. The `ENGINE` is `'django.db.sqlite3'`. You can also inspect the INSTALLED_APPS, which contain some django apps. These apps require changes to the database and "cause" the previous warnings about migrations. These warnings are fixed by:  
    ```console
    $python mangage.py migrate
    ```
## Change the models
- Change your **models.py**
- Run ```python manage.py makemigration``` to create the migrations
    - You add the created migrations to your version control system
- run ```python manage.py migrate`` to apply the migrations
- play with your models by running a python REPL:  
    ```python manage.py shell```
- generally you want to implement the ```__str__(self):``` method