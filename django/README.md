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
