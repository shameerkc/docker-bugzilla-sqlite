Docker Bugzilla using SQLite
============================

Configure a running Bugzilla system using Docker. The project is built on top of the existing [https://github.com/bugzilla/docker-bugzilla-dev](https://github.com/bugzilla/docker-bugzilla-dev) project, with the only difference being that instead of MySQL, Sqlite is used as the internal Database.

## Features

* Sqlite is used as the internal DB.
* Please refer [Parent Project](https://github.com/bugzilla/docker-bugzilla-dev) for more details
* Preconfigured with initial data and test product

## How to install Docker

Visit [Docker][docker] and get Docker up and running on your system. Optionally
you could install [Docker Compose](docker-compose)
to help with setting up a new container.

## How to build Bugzilla Docker image

To build a fresh image, just change to the directory containing the checked out
files and run the below command:

```bash
$ docker-compose build
```
## How to start Bugzilla Docker image

To start a new container (or rerun your last container) you simply do:

```bash
$ docker-compose up
```

This will stay in the foreground and you will see the output from `supervisord`. You
can use the `-d` option to run the container in the background.

To stop, start or remove the container that was created from the last run, you can do:

```bash
$ docker-compose stop
$ docker-compose start
$ docker-compose rm
```

## How to access the Bugzilla container

If you are using Linux, you can simply point your browser to
`http://localhost:8089/bugzilla/` to see the the Bugzilla home page.

The Administrator login is `admin` and the password is `password`.
You can use the Administrator account to creat other users, add products or
components, etc.

You can also login to the container using `docker exec -it bugzilla-dev-sqlite su - bugzilla` command.
You can run multiple containers but you will need to give each one a different name/hostname
as well as non-conflicting ports numbers for httpd and vnc.

## TODO

* No changes are planned now.

[docker]: https://docs.docker.com/installation/
[docker-compose]: https://docs.docker.com/compose/install/
