# Documentation

The annotation tool is built using the Django library for it's SQLite object-relational mapping. Core logic is written in Python in `core/views.py` and the database schema is specified in `core/models.py`. HTML templates are defined (with built-in Javascript scripts) in `core/templates`.

Dependency and virtual environment management is handled using pipenv.

## Initializing and launching backend
1. Install dependencies using
```
pipenv install
```
3. Create SQLite database with
```
pipenv run python manage.py makemigrations core
```
4. Migrate SQLite database:
```
pipenv run python manage.py migrate
```
5. Populate database with a sample Math Word Problem generation:
```
pipenv run python populate_database.py --generations_path=generations/mwp.json --version=1.0.0
```
6. Run the server:
```
pipenv run python manage.py runserver
```

## Migrating Database
1. Create migrations by running `pipenv run python manage.py makemigrations core`.
2. Run migrations by running `pipenv run python manage.py migrate`.
3. Source `env.sh` to connect to the production database and repeat the previous two steps.
4. Commit migration files (e.g. `core/migrations`) to version control.

## Dumping/Loading database
1. To dump the entire database to json run `pipenv run python manage.py dumpdata > db.json`.
2. To restore the database from a dump run `pipenv run python manage.py loaddata db.json`.


## Troubleshooting
If you are getting an error that your building wheel for mysqlclient failed
after running `pipenv install` on OSX, then run this line:
`export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/opt/openssl/lib/`
