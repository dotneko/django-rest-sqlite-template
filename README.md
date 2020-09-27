# Dockerized Django and Django REST Framework

Basic Django 3 and Django REST Framework template

## Installation

- Setup and activate virtual environment
- Install requirements with `pip install -r requirements.txt` in `/backend` directory
- Place Django's `SECRET_KEY` in `/backend/dj_secret.key`

## Build and Test Dockerfile

To build:

```
docker build -t test_drf backend
```

To run:

```
docker run -p 51010:8000 -it test_drf
```

Check successful build by accessing page via browser at http://localhost:51010

## Launch with docker-compose

Launch with `docker-compose` with host directory mounted in container:

```
docker-compose up
```

For migrations and createsuperuser, first execute a shell into running container:

```
docker-compose exec backend /bin/bash
```

*Then at bash shell:*

```
python manage.py migrate
python manage.py createsuperuser
```

### Note:

* Using just the Dockerfile does not provide access to the host files and therefore `db.sqlite3` cannot be updated.
* Attempted to run docker with bind mount / volume options but unsuccessful on Ubuntu from WSL2 (?bug)
