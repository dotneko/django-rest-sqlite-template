# Dockerized Django and Django REST Framework

Basic Django 3 and Django REST Framework template

## Installation

- Setup and activate virtual environment
- Install requirements with `pip install -r requirements` in `/backend` directory
- Place Django's `SECRET_KEY` in `/backend/dj_secret.key`

## Build and Test

To build:

```
docker build -t test_drf backend
```

To run:

```
docker run -p 8000:8000 -t test_drf:latest
```

Check successful installation by accessing page via browser at http://localhost:8000
