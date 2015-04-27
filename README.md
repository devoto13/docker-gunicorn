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

Environment variables (defaults are the same as Gunicorn defaults if opposite is not stated explicitly):

* `APP_WSGI` - **REQUIRED.** WSGI application to run.
* `APP_NAME` - **REQUIRED.** Corresponds [proc_name](http://docs.gunicorn.org/en/latest/settings.html#proc-name).
* `APP_WORKERS` - Corresponds [workers](http://docs.gunicorn.org/en/latest/settings.html#workers).
* `BIND` - Corresponds [bind](http://docs.gunicorn.org/en/latest/settings.html#bind) (default: 0.0.0.0:80).
* `WORKER_CLASS` - Corresponds [worker_class](http://docs.gunicorn.org/en/latest/settings.html#worker-class).
* `WORKER_CONNECTIONS` - Corresponds [worker_connections](http://docs.gunicorn.org/en/latest/settings.html#worker-connections).
* `BACKLOG` - Corresponds [backlog](http://docs.gunicorn.org/en/latest/settings.html#backlog).
* `MAX_REQUESTS` - Corresponds [max_requests](http://docs.gunicorn.org/en/latest/settings.html#max-requests).
* `TIMEOUT` - Corresponds [timeout](http://docs.gunicorn.org/en/latest/settings.html#timeout).
* `GRACEFUL_TIMEOUT` - Corresponds [graceful_timeout](http://docs.gunicorn.org/en/latest/settings.html#graceful-timeout).
* `KEEPALIVE` - Corresponds [keepalive](http://docs.gunicorn.org/en/latest/settings.html#keepalive).

You pass with `-e` docker option.

Usage
-----

Image intended to be used as base image for another `Dockerfile`. Take a look at the `example/` directory.
