
# ConnectNest

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

### Database connections
Go to ```mis/mis/settings.py```
```sh
from dotenv import load_dotenv
from os.path import join, dirname
# Create .env file path.
dotenv_path = join(dirname(__file__), 'dev.env')
# Load file from the path.
load_dotenv(dotenv_path)
# get the secret key from env file
SECRET_KEY = os.getenv('SECRET_KEY')
# get the database variables from env file
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': os.getenv('DB_NAME'),
        'USER': os.getenv('DB_USER'),
        'PASSWORD': os.getenv('DB_PASSWORD'),
        'HOST': os.getenv('DB_HOST'),  
        'PORT': os.getenv('DB_PORT'),
    }
}
```
### Database
Migrations are Django’s way of propagating changes you make to your models (adding a field, deleting a model, etc.) into your database schema. They’re designed to be mostly automatic, but you’ll need to know when to make migrations, when to run them, and the common problems you might run into.

what migrations will do is,
1. It will go to settings.py and get INSTALLED_APPS
2. within these installed apps directory it will go to models and create schema for whatever class you have specified.

```
cd mis
# responsible for applying and unapplying migrations.
python manage.py makemigrations
# creating new migrations based on the changes you have made to your models.
python manage.py migrate --fake loan_insight

```

Licence
---
© 2020   GNU GENERAL PUBLIC LICENSE Version 2, June 1991
