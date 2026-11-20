# StaticJinjaPlus Docker Port

Docker images for [StaticJinjaPlus](https://github.com/MrDave/StaticJinjaPlus).

This repository contains Dockerfiles for building StaticJinjaPlus images using different base images.

The source code is downloaded directly from the original GitHub repository during the image build. The port does not contain a copy of the upstream source code.

## Available Dockerfiles

- `Dockerfile.ubuntu` — based on Ubuntu 24.04 LTS.
- `Dockerfile.python-slim` — based on the official Python Slim image.

## Choosing the StaticJinjaPlus version

Both Dockerfiles support the `SOURCE_REF` build argument.

To build a tagged release, use:

```bash
--build-arg SOURCE_REF=refs/tags/0.1.1
```

To build the latest code from the main branch, use:

```bash
--build-arg SOURCE_REF=refs/heads/main
```

## Build with Ubuntu

Build from release 0.1.1:

```bash
docker build -f Dockerfile.ubuntu \
  -t static-jinja-plus:ubuntu-0.1.1 \
  --build-arg SOURCE_REF=refs/tags/0.1.1 .
```

Build from main:

```bash
docker build -f Dockerfile.ubuntu \
  -t static-jinja-plus:ubuntu-main \
  --build-arg SOURCE_REF=refs/heads/main .
```

## Build with Python Slim

The Python version can be selected with the `PYTHON_VERSION` build argument.

Build with Python 3.15 from release 0.1.1:

```bash
docker build -f Dockerfile.python-slim \
  -t static-jinja-plus:python315-0.1.1 \
  --build-arg PYTHON_VERSION=3.15 \
  --build-arg SOURCE_REF=refs/tags/0.1.1 .
```

Build with Python 3.15 from main:

```bash
docker build -f Dockerfile.python-slim \
  -t static-jinja-plus:python315-main \
  --build-arg PYTHON_VERSION=3.15 \
  --build-arg SOURCE_REF=refs/heads/main .
```

## Run a container

For example:

```bash
docker run --rm static-jinja-plus:ubuntu-0.1.1
```