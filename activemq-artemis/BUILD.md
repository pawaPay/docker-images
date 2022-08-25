# Building the ActiveMQ Artemis Docker Image

Depending on your platform the build process may differ slightly. Support for as many build platforms as possible is provided in a best effort basis.

## Prerequisites

To build the ActiveMQ Artemis Docker Image the following tools are necessary:

- Docker

## Supported Platforms

Only UN*X based operating systems are supported currently for building this image.

## Building the image

You can build the image locally, the dockerfile is present under `src` folder and pass in the `ACTIVEMQ_ARTEMIS_VERSION` as builder arg to whichever version you want. e.g

```bash
cd src/
docker build --builder-arg ACTIVEMQ_ARTEMIS_VERSION=2.17.0 -t activemq-artemis-docker .
```

## Building through pipeline

We have setup Github Actions for building the image and pushing to our Dockerhub, if you wish to change anything, you can update the Dockerfile or if you update the version of ActiveMQ Artemis, update the workflow file to update the ARG `ACTIVEMQ_ARTEMIS_VERSION` and create a PR, which will build the image, once successful, you can merge the PR and it will create a tag incrementing the patch version. If you wish to update the minor version e.g. when updating `ACTIVEMQ_ARTEMIS_VERSION`, you can update the `DEFAULT_BUMP:` to `minor` in `.github/workflows/master.yaml` at the 2 places.
