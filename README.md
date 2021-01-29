# cookiecutter-docker-django
A cookiecutter template for deploying a Django projects with docker-compose. This template for Django is inspired by [Pydanny's cookiecutter](https://github.com/pydanny/cookiecutter-django).
The goal is optimize development processes, fast and ready to use with docker compose, [12 Factor](https://12factor.net/) based settings and the folowing features:

* **Django** 3.0+
* **Python** 3.9
* **NGINX** configuration for production environment.
* **SSL** certificate for **Nginx**.
* **PostgreSQL** as database engine.
* **Whitenoise**
* [**Anymail**](https://github.com/anymail/django-anymail) integretion using [**Mailgun**](https://www.mailgun.com/)
* As media storage can choice between Azure, AWS or Google Cloud
* Fully dockerized, local development via **docker-compose**
* Optional **Django Rest Framework** integration
* **Celery** (optional) and **Redis** settings.

## Quick Start
First, install [cookiecutter](https://github.com/audreyr/cookiecutter)
```bash
$ pip install cookiecutter
```

And the, scaffold the project:
```bash
$ cookiecutter https://github.com/ezecavallo/cookiecutter-docker-django.git
```

## Configuration
Before starting, I strongly recommend reviewing the files. While the configuration is ready for a local environment, remember to check and set the production environment variables, as well you need to generate SSL certificates before run docker-compose in a web server.

To generate the certificates run the script *cert-entrypoint* (written by [**Philipp**](https://github.com/wmnnd/nginx-certbot) [@wmnnd](https://github.com/wmnnd)) following the next commands:
```bash
$ sed -i -e 's/\r$//' cert-entrypoint.sh

$ chmod +x cert-entrypoint.sh

$ sudo ./cert-entrypoint.sh
```

## Stack
The stack consist of:
* django
* postgresql
* nginx
* celerybeat
* celeryworker
* flower
* redis

## Contributing

If you want to contribute, please feel free to submit pull requests.</br>
Suggestions are welcome!
