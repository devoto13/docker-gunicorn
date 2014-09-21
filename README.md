docker-gunicorn
---------------

Docker gunicorn server generic image source. This is based on `ubuntu:14.04` image.

Image
-----

You can `pull` a ready to use image from Docker
[index](https://index.docker.io/u/devoto13/) running:

```
$ docker pull devoto13/gunicorn
```

Or build this repository:

```
$ git clone https://github.com/devoto13/docker-gunicorn.git
$ cd docker-gunicorn/
$ docker build -t devoto13/gunicorn .
```

Change `devoto13/gunicorn` to your Docker index username.

Container
---------

This image uses volumes and environment variables to control the gunicorn server
configuration.

Volumes:

* `/root/app/logs`: Logs from the container using it.

You pass with `-v` docker option. Don't forget to use absolute path here.

Environment variable:

* `APP_WSGI`: WSGI application to run.
* `APP_NAME`: Application label.
* `APP_WORKERS`: Number of workers to run.

You pass with `-e` docker option.

Usage
-----

Image intended to be used as base image for another `Dockerfile`. Take a look at the `example/` directory.
