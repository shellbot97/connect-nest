
# ConnectNest

- connect univerity/college aspirant with top students already studying in their desired institution.  

---

### Build Status - 
| Branch | Status |
| ------ | ------ |
| Master | Live |
| auth | Dev |
| profile | UAT |
| feature3 | merged-master-Live |

This is the repository dedicated for handling version control of ConnectNest.

### Installation

ConnectNest requires [DJANGO](https://www.djangoproject.com/) v2.2.4 to run.

Make project folder,
```sh
 $ » mkdir connectnest
 $ » cd connectnest
```

Clone this repository inside folder connectnest, it comes with,

1. Virtual Environment named cnest_env
2. requirements.txt containing all the packages, required for development of this project.
3. Base strucure of project connectnet, having following directory structure,

```
..
└── connectnest
    ├── cnest
    |   ├── cnest
    |   │   ├── dev.env
    |   │   ├── __init__.py
    |   │   ├── local.env
    |   │   ├── prod.env
    |   │   ├── __pycache__
    |   │   ├── settings.py
    |   │   ├── urls.py
    |   │   └── wsgi.py
    |   ├── auth
    |   │   ├── admin.py
    |   │   ├── apps.py
    |   │   ├── __init__.py
    |   │   ├── migrations
    |   │   ├── models.py
    |   │   ├── tests.py
    |   │   └── views.py
    |   ├── profile
    |   │   ├── admin.py
    |   │   ├── apps.py
    |   │   ├── __init__.py
    |   │   ├── migrations
    |   │   ├── models.py
    |   │   ├── tests.py
    |   │   └── views.py
    |   ├── feature3
    |   │   ├── admin.py
    |   │   ├── apps.py
    |   │   ├── __init__.py
    |   │   ├── migrations
    |   │   ├── models.py
    |   │   ├── tests.py
    |   │   └── views.py
    ├── cnest_env
    │   ├── bin
    │   ├── include
    │   └── lib
    ├── README.md
    └── requirements.txt
```
```

Start Virtual Environment,
```sh
 $ /connectnest» source cnest_env/bin/activate
```

Now install the packages we require from ```requirement.txt``` with the command,
```sh
(cnest_env) $ /loans» pip install -r requirements.txt
```

To make sure the installation is done properly,
```
python manage.py runserver
```
this will start the dev server on ```127.0.0.1:8000```, where you will see the django-introduction page. 

### Environment variables
| variable | use |
| ------ | ------ |
| SECRET_KEY | ```settings.py``` |
| DEBUG_STATUS | ```settings.py``` |
| DB_NAME | ```settings.py``` |
| DB_USER | ```settings.py``` |
| DB_PASSWORD | ```settings.py``` |
| DB_HOST | ```settings.py``` |
| DB_PORT | ```settings.py``` |


### Database
Migrations are Django’s way of propagating changes you make to your models (adding a field, deleting a model, etc.) into your database schema. They’re designed to be mostly automatic, but you’ll need to know when to make migrations, when to run them, and the common problems you might run into.

what migrations will do is,
1. It will go to settings.py and get INSTALLED_APPS
2. within these installed apps directory it will go to models and create schema for whatever class you have specified.

```
cd connectnest
# responsible for applying and unapplying migrations.
python manage.py makemigrations

```

Licence
---
© 2020   GNU GENERAL PUBLIC LICENSE Version 2, June 1991
