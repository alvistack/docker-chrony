# Docker Image Packaging for Chrony

[![Travis](https://img.shields.io/travis/alvistack/docker-chrony.svg)](https://travis-ci.org/alvistack/docker-chrony)
[![GitHub release](https://img.shields.io/github/release/alvistack/docker-chrony.svg)](https://github.com/alvistack/docker-chrony/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/docker-chrony.svg)](https://github.com/alvistack/docker-chrony/blob/master/LICENSE)
[![Docker Pulls](https://img.shields.io/docker/pulls/alvistack/chrony.svg)](https://hub.docker.com/r/alvistack/chrony/)

Chrony is a versatile implementation of the Network Time Protocol (NTP).

Learn more about Chrony: <https://chrony.tuxfamily.org/>

## Supported Tags and Respective `Dockerfile` Links

  - [`latest` (master/Dockerfile)](https://github.com/alvistack/docker-chrony/blob/master/Dockerfile)
  - [`3.2` (3.2/Dockerfile)](https://github.com/alvistack/docker-chrony/blob/3.2/Dockerfile)

## Overview

This Docker container makes it easy to get an instance of Chrony up and running.

### Quick Start

Start Chrony:

    # Pull latest image
    docker pull alvistack/chrony
    
    # Run as detach
    docker run \
        -itd \
        --cap-add SYS_TIME \
        --name chrony \
        --publish 123:123/udp \
        alvistack/chrony
    
    # Run with custom /etc/chrony/chrony.conf
    docker run \
        -itd \
        --cap-add SYS_TIME \
        --name chrony \
        --publish 123:123/udp \
        --volume /etc/chrony/chrony.conf:/etc/chrony/chrony.conf \
        alvistack/chrony

**Success**. Chrony is now available on port `123/udp`.

## Versioning

The `latest` tag matches the most recent version of this repository. Thus using `alvistack/chrony:latest` or `alvistack/chrony` will ensure you are running the most up to date version of this image.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
