ucoin_site
==========

Ucoin website : http://ucoin.io

Install App
===========

First, you need to setup an isolated developement environment for the
python apps using virtualenv_. If you don't have virtualenv_, you can
install it using your package manager such as *apt* if you're on
debian:

    apt-get install virtualenv
    virtualenv --no-site-packages ucoin-env

Then, enters the environment:

    cd ucoin-env
    source bin/activate
  
Your prompt should update to something like (note the prefix):

    (ucoin-env)glibersat@carpe:~/Source/ucoin-env

.. warning:: For all next steps, you need to be in an activated environment.
  
  
Getting the code
================

Once you're in your virtualenv directory, use::

    git clone https://github.com/SimonSarazin/ucoin_site
    cd ucoin_site
  
fetch the dependencies using::

    pip install -r requirements.txt
  
*It may be the right time to get a cup of coffee! :-)*

.. note::

  From now on, the ``ucoin_site`` directory will be called **the project root** (or **PROJECT_ROOT**).


Populating the Database
=======================

You can use the actual "project.db" as an example, with an already completed homepage.

(optionnal) If you want to a new sqlite database. you need to initialize it with these commands::

    python manage.py syncdb --all
    python manage.py migrate --fake
    python manage.py check_permissions


(optionnal) Django will prompt for a user creation, this is always a good idea to say *yes*::

     You just installed Django's auth system, which means you don't have any superusers defined.
     Would you like to create one now? (yes/no): **yes**

(optionnal) You could also configure a database server on PostGreSQL_. It is recommended for large website


Now, run the server::

    python manage.py runserver

Admin login/password is "admin/admin"


Licenses
========

This software is licensed under the AGPLv3 (See COPYING file for more information).

The media (pictures, sounds, videos, ...) are licensed under the Creative Commons CC-BY-SA (See MEDIA_COPYING for more information).
