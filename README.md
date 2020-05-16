IITH Alumni portal
==================

This project will host code for the IITH Alumni portal.

Installation
------------

Install `pip` and then install system-wide `virtualenv` PIP package.

    sudo apt-get install python-pip
    sudo pip install virtualenv

Create a virtual environment for our current `alumni-portal` project in a
folder named `.venv`, and "activate" it, so that all our subsequent PIP
packages are installed in this virtual environment only, and not globally. Note
that you don't require `sudo` access any more to install PIP packages in this
local virtual environment.

    cd alumni-portal
    virtualenv .venv
    source .venv/bin/activate


Install the dependencies using:

    pip install -r requirements.txt

**Note:** Above command installs Django also.

Running the Django app
----------------------

Create SQLite database, which is just a file `db.sqlite3` being used as
database for this app.

    python manage.py migrate

And then run the Django app

    python manage.py runserver

Now you can go to your browser and type `http://127.0.0.1:8000/` and you can
see the Django app in action!

Run google auth 
---------------

Google auth needs a google application to be created. The url has been given as 'iith-alumni.com' which has to be used to run the application, Edit the etc hosts in your system 

    sudo vi /etc/hosts

and add the following line

    127.0.0.1       iith-alumni.com

Insert data required for registration
-------------------------------------

The standard Departments and Degrees can added to the database by running the following command

    python manage.py shell < portalapp/dml.py

How to contribute
-----------------
GitHub Issues will be used to track all the new features to be developed, and
also for bugs. If you want to contribute then fork the repo to your own github
account and create a branch with your changes and then create a pull request.
People who have push access to the repo, please don't push code directly to the
repo. Follow the above procedure. It helps to have someone else look into your
changes.
