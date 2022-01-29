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

## start a django app for your website.
- In the root folder run the following command, this creates the polls app, ofcourse you can specify a name of your own.
   ```shell
   python mangage.py startapp polls
   ```