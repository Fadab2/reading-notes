# Django REST Framework & Docker
## Docker

* Docker is used to isolate and run applications using Linux containers.
* Docker makes it possible to run applications regardless of the OS your system running.
* Docker makes it possible to reproduce production environment locally and share with team members.
* We need to install Docker before we can use it.
* We also need to install docker-compose using `sudo pip install docker-compose` if using Linux otherwise it is included.
* `docker-compose --version` to check compose is installed.

### Images and Containers

* An image is a snapshot in time of what a project contains. A container is a running instance of the image.
* To create an image we can create a direcotry, cd to the directory then create an image `touch Dockerfile` and adding `# Dockerfile
FROM python:3.7-alpine` to the file.
* To create the image for the first time we run ` docker image build .`
* To create an app and new project using and using `pipenv` as a local environment we run the following commands.
```
mkdir djangoapp && cd djangoapp
pipenv install django==3.0
pipenv shell
django-admin startproject example_project .
python manage.py runserver
```
* To create Dockerfile for our image to replace our local environment: 
```
touch Dockerfile
touch docker-compose.yml

```

## Django REST Framework

* Django REST Framework works Django web framework to create web APIs.
* Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON.
To create a new directory and virtual environment and activate it using:
```
mkdir library
cd library
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install django~=4.0.0
```
Adding Django REST Framework just run the command to install it: 
`python -m pip install djangorestframework~=3.13.0`
Update the setting.py file with `  "rest_framework",  ` on the installed apps section.
We create and update a views.py file as follows:
```
from rest_framework import generics

from books.models import Book
from .serializers import BookSerializer


class BookAPIView(generics.ListAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer

```

<br />

## References


[A Beginner's Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)

[Library Website](https://djangoforapis.com/library-website-and-api/)

<br />

## [<-- Back](README.md)
