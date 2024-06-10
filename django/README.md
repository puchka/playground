# Installation

Create a virtual environment using `virtualenv`

```sh
python -m virtualenv .venv
source .venv/bin/activate
```

Install Django

```sh
touch requirements.txt
echo 'django' > requirements.txt
pip install -r requirements.txt
```

## Verifying

To verify that Django can be seen by Python, type python from your
shell. Then at the Python prompt, try to import Django:

```
>>> import django
>>> print(django.get_version())
5.0.6
>>> 
```

You may have another version of Django installed.

Type `C-Z` to exit the Python prompt.

## Reference

- https://docs.djangoproject.com/en/5.0/intro/install/

# Tutorial 1: Writing your first Django app, part 1

Another way to check if Django is installed and it's version.

```sh
python -m django --version
```

If Django is installed, you should see the version of your
installation. If it isn’t, you’ll get an error telling “No module
named django”.

```sh
$ django-admin startproject mysite
```

This will create a mysite directory in your current directory.

```sh
$ tree mysite/
mysite/
├── manage.py
└── mysite
    ├── asgi.py
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py

1 directory, 6 files
```

```sh
cd mysite
python manage.py runserver
```

```
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
May 27, 2024 - 15:50:39
Django version 5.0.6, using settings 'mysite.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.


```

Open the URL http://127.0.0.1:8000/ in a web browser will show a page with a rocket taking off.

## Reference

- https://docs.djangoproject.com/en/5.0/intro/tutorial01/

# Creating the Polls app

```sh
$ python manage.py startapp polls
```

```sh
$ tree django/mysite/polls/
django/mysite/polls/
├── admin.py
├── apps.py
├── __init__.py
├── migrations
│   └── __init__.py
├── models.py
├── tests.py
└── views.py

1 directory, 7 files
```

After wiring index view into URLConf you can check the result in the
browser at the URL: http://localhost:8000/polls/ after running:

```sh
$ python manage.py runserver
```

# Tutorial 2: Writing your first Django app, part 2

## Database setup

Install `sqlite3`, a command-line interface for SQLite 3.

```sh
sudo apt install sqlite3
```

```sh
sqlite3 mysite/db.sqlite3
```

and

```sh
sqlite> .tables
```

to list the tables.

e.g

```
auth_group                  auth_user_user_permissions
auth_group_permissions      django_admin_log          
auth_permission             django_content_type       
auth_user                   django_migrations         
auth_user_groups            django_session
```

To run the migrations related the `INSTALLED_APPS` in `mysite/settings.py`

```sh
$ python manage.py migrate
```
