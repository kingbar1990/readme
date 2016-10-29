# Install
    sudo apt-get install postgresql

# Login to postgres
    sudo -u postgres psql

# Work with SQL
    CREATE DATABASE <name>;
    CREATE USER <login> WITH password '<password>';
    GRANT ALL privileges ON DATABASE <name> TO <login>;

# Django
    DATABASES = {
        'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': <name>,
        'USER': <login>,
        'PASSWORD': <password>,
        'HOST': '', # Set to empty string for localhost.
        'PORT': '', # Set to empty string for default.
        }
    }
