# Create the project directory\
```bash
mkdir tutorial
cd tutorial
```
# Create a virtualenv to isolate our package dependencies locally
```bash
virtualenv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
```

# Install Django and Django REST framework into the virtualenv
```bash
pip install django
pip install djangorestframework
```

# Set up a new project with a single application
```bash
django-admin.py startproject tutorial .  # Note the trailing '.' character
cd tutorial
django-admin.py startapp quickstart
cd ..
```
