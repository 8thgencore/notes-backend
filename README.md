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