```shell
# supposed you have python3 installed and added in PATH

cd /path/to/outer/mysite

# step 0. Create virtual environment for this app
# https://virtualenv.pypa.io/en/stable/userguide/

# step 1. Install requirements
pip install -r requirements.txt

# step 2. Create database (will NOT create a default super user: admin/admin)
          Create migration for changes in models for polls app
          Print SQL what Django think, doesn’t actually run the migration on your database
          Apply all migrations to the database
python manage.py migrate
python manage.py makemigrations polls
python manage.py sqlmigrate polls 0001
python manage.py migrate

# step 3. create super user (optional, see step 2)
python manage.py createsuperuser

# step 4. collect static files (optional, for deployment)
python manage.py collectstatic

# step 5. start the web server (for site preview or development)
python manage.py runserver

# step 6. Runs your tests and collects coverage data of the executed files in your project
python manage.py test polls
coverage run --source='.' manage.py test polls
coverage report
```