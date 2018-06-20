# Django Gunicorn Nginx
Base image for Django With PostgreSQL and Redis

This is my attempt at automating my old pipeline. I wanted to save this somewhere before I flatten,
and start a better one.


Edit the `*.env` files to edit configuration for your staging environment.


```
mv example.docker-compose.yml docker-compose.yml
# SET SECURITY, ENVIRONMENT OR
# SOURCE `envars`
. envars
# AND EXECUTE THE NECESSARY FUNCTIONS
set_env
set_sec
docker-compose build --force-rm
docker-compose up -d
# INIT DATABSE IF NECESSARY
init_database
```

### Django Migrations  

And then learn Django, but not necessarily in that order :)

```
docker-compose run web python manage.py migrate
docker-compose run web python manage.py makemigrations polls
docker-compose run web python manage.py sqlmigrate polls 0001
```


#### Getting Started With Django
For more information refer to th Django [Introduction](https://docs.djangoproject.com/en/2.0/intro)

