# notes-backend

lesson: https://testdriven.io/blog/dockerizing-django-with-postgres-gunicorn-and-nginx

# Add .env file

*.env.dev*
```
DEBUG=1
SECRET_KEY='django-insecure-mykey'
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]

SQL_ENGINE=django.db.backends.postgresql
SQL_DATABASE=mydb_dev
SQL_USER=mydb
SQL_PASSWORD=mydb
SQL_HOST=db
SQL_PORT=5432
DATABASE=postgres
```

*.env.prod*
```
DEBUG=0
SECRET_KEY='django-insecure-mykey'
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]

SQL_ENGINE=django.db.backends.postgresql
SQL_DATABASE=mydb_prod
SQL_USER=mydb
SQL_PASSWORD=mydb
SQL_HOST=db
SQL_PORT=5432
DATABASE=postgres
```

*.env.prod.db*
```
POSTGRES_USER=mydb
POSTGRES_PASSWORD=mydb
POSTGRES_DB=mydb_prod
```

### Run
```
docker-compose -f docker-compose.prod.yml up -d --build
docker-compose -f docker-compose.prod.yml exec web python manage.py makemigrations   
docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear
docker-compose -f docker-compose.prod.yml exec web python manage.py createsuperuser
```
