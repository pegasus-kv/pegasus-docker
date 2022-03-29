# Pegasus Docker

This project maintains the stuff you can use from building Pegasus docker images,
to deploying a standalone cluster of Pegasus containers on your local machine.

## Workflows

![Build and publish multi pegasus-build-env Docker images](https://github.com/pegasus-kv/pegasus-docker/workflows/build-push-env-docker.yml/badge.svg?branch=master)

![Build and publish multi thirdparty Docker images](https://github.com/pegasus-kv/pegasus-docker/workflows/thirdparty-regular-push.yml/badge.svg?branch=master)

![Build pegasus/rdsn regularly everyday base env and thirdparty docker](https://github.com/pegasus-kv/pegasus-docker/workflows/pegasus-regular-build.yml/badge.svg?branch=master)

## pegasus-build-env

Building environment for Pegasus compilation.

Github Actions automatically rebuilds and publishes build-env for every commit.

- `apachepegasus/build-env:centos7`
- `apachepegasus/build-env:ubuntu1604`
- `apachepegasus/build-env:ubuntu1804`
- `apachepegasus/build-env:ubuntu2004`

DockerHub: https://hub.docker.com/r/apachepegasus/build-env

The How-to-use Manual is at: http://pegasus.apache.org/docs/build/compile-by-docker/

## thirdparties-src

This image is to eliminate extra downloading of third-party sources of Pegasus.
It packages the downloaded sources into a zip in the container, so that
other repos can easily extract third-parties from the container (via `docker cp`),
without downloading from the cloud object storage.

- `apachepegasus/thirdparties-src`

## thirdparties-bin

This is a Docker image for Pegasus unit-testing. It prebuilts the thirdparty libraries,
so jobs based on this image can skip building third-parties.

- `apachepegasus/thirdparties-bin:centos7`
- `apachepegasus/thirdparties-bin:ubuntu1604`
- `apachepegasus/thirdparties-bin:ubuntu1804`
- `apachepegasus/thirdparties-bin:ubuntu2004`
