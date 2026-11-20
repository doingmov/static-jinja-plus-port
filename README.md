
# StaticJinjaPlus Docker Port

Docker images for [StaticJinjaPlus](https://github.com/MrDave/StaticJinjaPlus).

This repository contains Dockerfiles for building StaticJinjaPlus images using different base images.

The source code of StaticJinjaPlus is downloaded directly from the original GitHub repository during the image build.

## Available Dockerfiles

- `Dockerfile.ubuntu` — based on Ubuntu 24.04.
- `Dockerfile.python-slim` — based on Python Slim (Debian Bookworm).

## Build with Ubuntu

Build an image using StaticJinjaPlus version 0.1.1:

```bash
docker build \
  -f Dockerfile.ubuntu \
  -t static-jinja-plus:0.1.1-ubuntu \
  --build-arg SOURCE_VERSION=0.1.1 \
  .
```

Run the container:

```bash
docker run --rm static-jinja-plus:0.1.1-ubuntu
```

## Build with Python Slim

Build an image using StaticJinjaPlus version 0.1.1:

```bash
docker build \
  -f Dockerfile.python-slim \
  -t static-jinja-plus:0.1.1-slim \
  --build-arg SOURCE_VERSION=0.1.1 \
  .
```

Run the container:

```bash
docker run --rm static-jinja-plus:0.1.1-slim
```

## Choosing StaticJinjaPlus version

The `SOURCE_VERSION` build argument specifies the version tag of StaticJinjaPlus to download from GitHub.

For example, to build version 0.1.0, replace:

```bash
--build-arg SOURCE_VERSION=0.1.1
```

with:

```bash
--build-arg SOURCE_VERSION=0.1.0
```

The same argument works with both Dockerfiles.

## Choosing a base image

Select the required base image by choosing the corresponding Dockerfile:

- `Dockerfile.ubuntu` for Ubuntu.
- `Dockerfile.python-slim` for Python Slim.
