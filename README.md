# install_django_mongodb
A tutorial for installing Django with MongoDB for use in 67-372 (Advanced Application Design and Development)

## Content to Install
Here is an overview of the programs we will install and integrate together in a sample Django project for the purposes of being able to quickly instantiate a project running on Django/MongoDB:

1. Python 3.4.X (here we will install Python 3.4.7)
2. Django (via pip, the Python Package Installer installed by default)
3. MongoDB (3.4)
4. mongoengine (http://mongoengine.org/)


### 1. Installing Python

This semester, we have decided to instruct 67-372 Advanced Application Design and Development using the Python/Django stack for creating web applications. Doing so gives the flexibility of learning how to develop sleek, modern web applications in an easy-to-understand format. Python/Django is actually used by many enterprises looking to create robust web applications to help suit the mission of the greater organization, and so having some Python/Django experience will not only allow for a relatively smooth transition into the general world of web applications, but can help provide some tangible work which can easily be applied to outside organizations.

From 15-112: Fundamentals of Programming and Computer Science (for those of you who have taken it), you should be familiar with the Python language. You can refresh your Python programming skills by visiting [this python tutorial site](https://www.learnpython.org/).

Please be sure to install Python 3.4.X on your machine. The download link is [here](https://www.python.org/downloads/).

**Be sure to check the 'Add Python to Path' option in the installer!**

Once you have installed Python on your machine, please be sure to add it to your path.

#### Installing to the Path

**Be sure to check the 'Add Python to Path' option in the installer!**, this will add Python to your system environment variables so you can use it from the command line from any directory. 

**If you forgot to check this option in the installer, please uninstall Python and re-install being sure to check this option in the installer!**

#### Verifying Python Installation

You can verify Python is on your path by doing the following:

##### MacOS/Linux

1. Open Terminal
2. run `python --version`
3. If this shows “2.X”, try running `python3 --version`
4. If you see “Python 3.4.X” then you have it! (Note whether you typed in `python` or `python3` to get the desired version)

If not, try re-starting terminal or checking it is properly added to your path.

##### Windows

1. Open Command Prompt or Powershell
2. run `python --version`
3. If this shows “2.X”, try running `python3 --version`
4. If you see “Python 3.4.X” then you have it!

If not, try re-starting cmd/Powershell or checking it is properly added to your path.

### 2. Installing Django

Now we will install Django, the Python package which allows us to create web applications with relative ease. The installation process for Django is relatively simple, because it only requires **pip**, the Python Package Installer, to install.

**NOTE: For the following steps, if you got the correct version of Python to show from the command line by running the command `python3 --version`, please be sure to run `pip3` instead of `pip`! Same for using `python3` in place of `python`**

1. Open Terminal or the command line
2. run `pip install django`
3. If `pip` is seen as not install, try `python -m pip install django`
4. Let django install

#### Verifying Django Installation

Once Django has finished installing from the command line, then perform the following:
1. Open Terminal or the command line
2. run `python` to open the Python REPL
3. run `import django` from inside of the Python REPL.
4. If the next line is blank (or simply `>>>`), then Django is installed!
5. Again, check the version of Python to be 3.4.X (shown on the first line of the REPL)

### 3. Installing MongoDB

Please refer to [this guide](https://docs.mongodb.com/manual/administration/install-community/) for platform-specific instructions on installing MongoDB to your system.

#### Verifying MongoDB Installation

Try the following:
1. Open two terminal/command line shells or tabs.
2. On one terminal shell, run `mongod`. You should get a detailed log with no prompts to continue entering input.
3. On the other terminal shell, run `mongo`. You should get a prompt to run commands.
4. In the `mongo` shell, try running the mongo command `show dbs`. If you see several databases listed, everything is good to go!

### 4. Installing mongoengine

[mongoengine](http://mongoengine.org/) is a connector allowing for the use of a MongoDB database within a Django or Flask Python application (Django is supported, contrary to a graphic on their website).

There is extensive documentation on mongoengine, which you can find [here](http://mongoengine.readthedocs.io/en/latest/tutorial.html). **This will definitely come in handy during the semester**.

mongoengine can be installed with a simple pip install. Open terminal/command prompt and run the following command:

`pip install mongoengine`

#### Verifying mongoengine Installation

Once mongoengine has finished installing from the command line, then perform the following:
1. Open Terminal or the command line
2. run `python` to open the Python REPL
3. run `import mongoengine` from inside of the Python REPL.
4. If the next line is blank (or simply `>>>`), then mongoengine is installed!
5. Again, check the version of Python to be 3.4.X (shown on the first line of the REPL)

#### Connecting mongod and mongoengine

Down the line, we must connect the mongoengine to a running MongoDB server to access the database. You can start a new project by running `django-admin startproject <projectname>`.

1. Open Terminal or the command line.
2. Run `mongod` to start a local MongoDB server.
3. Open the django project `settings.py` file which can be found in the `<projectname>/<projectname>/settings.py`.
4. At the top of the `settings.py` file, we need to import the mongoengine library, so add `import mongoengine` after `import os`.
5. In the `settings.py` file, find the DATABASES variable, and modify it to:
```python
DATABASES = {
    'default': {
        'ENGINE': '',
    },
}
```
to remove the existing SQLite database.
6. Under the DATABASES variable, we will add the call to connect to the MongoDB server, running through our `mongod` call from step 2:
`mongoengine.connect(DB_NAME, host='mongodb://DB_USER:DB_USER_PASSWORD@localhost/DB_NAME')`
For more on the connection syntax, check out the [official documentation](http://mongoengine.readthedocs.io/en/latest/guide/connecting.html).
7. In a new Terminal/Command Line window, navigate into the greater `<projectname>` project directory and run `python manage.py runserver` to start the Django server.
8. If all is good, you will see new connections appear in the log of the `mongod` console, and you should be able to navigate to the address provided by django in the `python manage.py runserver` terminal/command line (http://127.0.0.1:8000/) with no issues.

### 5. Further Security and Sessions
TBD
