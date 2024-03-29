# MedFind
A medicine finder

## Run the project

* Clone it

* `virtualenv -p python3 env` //create env

  * install python3, pip, virtualenv if not installed
      *  `sudo apt-get install python3-dev python3-pip python3-virtualenv`

      *   `pip3 install virtualenv`
* config postgres `sudo apt-get install python-pip python-dev libpq-dev postgresql postgresql-contrib`
      * change user`sudo su - postgres`

      * `psql`

      * `CREATE DATABASE medfind;`

      * `CREATE USER medfindadmin WITH PASSWORD 'admin';`

      * `ALTER ROLE medfindadmin SET client_encoding TO 'utf8';`

      * `ALTER ROLE medfindadmin SET default_transaction_isolation TO 'read committed';`

      * `ALTER ROLE medfindadmin SET timezone TO 'UTC';`

      * `GRANT ALL PRIVILEGES ON DATABASE medfind TO medfindadmin;`

      * `\q`

      * `exit`
* `.env/bin/activate` //activate the env

* Run command `pip3 install -r requirements.txt`

* Change the settings.py DATABASE block and ALLOWED_HOSTS codes and values

  * `DATABASES = {
        'default': {
          'ENGINE': 'django.db.backends.postgresql_psycopg2',
          'NAME': 'medfind',
          'USER': 'medfindadmin',
          'PASSWORD': 'admin',
          'HOST': 'localhost',
          'PORT': '',
      }
  }`

  * `ALLOWED_HOSTS = ['localhost','127.0.0.1']`

  * `python manage.py makemigrations`

  * `python manage.py migrate`

  * `python manage.py createsuperuser
`
