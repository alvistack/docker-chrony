# Docker Image Packaging for Chrony

[![Travis](https://img.shields.io/travis/com/alvistack/docker-chrony.svg)](https://travis-ci.com/alvistack/docker-chrony)
[![GitHub release](https://img.shields.io/github/release/alvistack/docker-chrony.svg)](https://github.com/alvistack/docker-chrony/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/docker-chrony.svg)](https://github.com/alvistack/docker-chrony/blob/master/LICENSE)
[![Docker Pulls](https://img.shields.io/docker/pulls/alvistack/chrony.svg)](https://hub.docker.com/r/alvistack/chrony/)

Chrony is a versatile implementation of the Network Time Protocol (NTP).

Learn more about Chrony: <https://chrony.tuxfamily.org/>

## Supported Tags and Respective Packer Template Links

  - [`3.5`, `latest`](https://github.com/alvistack/docker-chrony/blob/master/packer/docker-3.5/packer.json)

## Overview

This Docker container makes it easy to get an instance of Chrony up and running.

Based on [Official Ubuntu Docker Image](https://hub.docker.com/_/ubuntu/) with some minor hack:

  - Packaging by Packer Docker builder and Ansible provisioner in single layer
  - Handle `ENTRYPOINT` with [catatonit](https://github.com/openSUSE/catatonit)

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

### `alvistack/chrony:latest`

The `latest` tag matches the most recent [GitHub Release](https://github.com/alvistack/docker-chrony/releases) of this repository. Thus using `alvistack/chrony:latest` or `alvistack/chrony` will ensure you are running the most up to date stable version of this image.

### `alvistack/chrony:<version>`

The version tags are rolling release rebuild by [Travis](https://travis-ci.com/alvistack/docker-chrony) in weekly basis. Thus using these tags will ensure you are running the latest packages provided by the base image project.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
