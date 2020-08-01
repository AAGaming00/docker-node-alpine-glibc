[![Docker Size](https://images.microbadger.com/badges/image/aadev00/node-alpine-glibc.svg)](http://microbadger.com/images/aadev00/node-alpine-glibc "Get your own image badge on microbadger.com")
[![Docker Stars](https://img.shields.io/docker/stars/aadev00/node-alpine-glibc.svg)](https://hub.docker.com/r/aadev00/node-alpine-glibc/)
[![Docker Pulls](https://img.shields.io/docker/pulls/aadev00/node-alpine-glibc.svg)](https://hub.docker.com/r/aadev00/node-alpine-glibc/)


NodeJS:Alpine GNU C library (glibc) Docker image
=========================================

Fork of [Meta's image](https://gitlab.com/metaa/docker-node-alpine-glibc/)

This image is based on the [NodeJS image](https://hub.docker.com/_/node/) using Alpine Linux as its base (`node:alpine`):  
[![](https://images.microbadger.com/badges/image/node:alpine.svg)](https://microbadger.com/images/node:alpine "Get your own image badge on microbadger.com")

It adds glibc to it to enable proprietary projects compiled against glibc (e.g. OracleJDK, Anaconda) work on Alpine.

This image includes some quirks to make [glibc](https://www.gnu.org/software/libc/) work side by
side with musl libc (default in Alpine Linux). glibc packages for Alpine Linux are prepared by
[Sasha Gerrand](https://github.com/sgerrand) and the releases are published in
[sgerrand/alpine-pkg-glibc](https://github.com/sgerrand/alpine-pkg-glibc) github repo.


Usage Example
-------------

This image is intended to be a base image for your NodeJS projects, so you may use it like this:

```Dockerfile
FROM aadev00/node-alpine-glibc

COPY ./my_app /usr/local/bin/my_app
```

```sh
$ docker build -t my_app .
```

This is based on GitHub user [`frol`'s repository](https://github.com/frol/docker-alpine-glibc) that adds glibc to the [Alpine image](https://hub.docker.com/_/alpine/) rather than the [NodeJS image with Alpine](https://hub.docker.com/_/node/).

