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

**NOTE: For the following steps, if you got the correct version of Python to show from the command line by running the command `python3 --version`, please be sure to run `pip3` instead of `pip`!**

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

#### Verifying MongoDB Installation

### 4. Installing mongoengine

#### Connecting MongoD and mongoengine

#### Verifying mongoengine Installation

