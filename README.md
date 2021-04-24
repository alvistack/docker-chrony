# Docker Image Packaging for Chrony

[![GitLab pipeline status](https://img.shields.io/gitlab/pipeline/alvistack/docker-chrony/master)](https://gitlab.com/alvistack/docker-chrony/-/pipelines)
[![GitHub release](https://img.shields.io/github/release/alvistack/docker-chrony.svg)](https://github.com/alvistack/docker-chrony/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/docker-chrony.svg)](https://github.com/alvistack/docker-chrony/blob/master/LICENSE)
[![Docker Pulls](https://img.shields.io/docker/pulls/alvistack/chrony-3.5.svg)](https://hub.docker.com/r/alvistack/chrony-3.5)

Chrony is a versatile implementation of the Network Time Protocol (NTP).

Learn more about Chrony: <https://chrony.tuxfamily.org/>

## Supported Tags and Respective Packer Template Links

  - [`alvistack/chrony-3.5`](https://hub.docker.com/r/alvistack/chrony-3.5)
      - [`packer/docker-3.5/packer.json`](https://github.com/alvistack/docker-chrony/blob/master/packer/docker-3.5/packer.json)

## Overview

This Docker container makes it easy to get an instance of Chrony up and running.

Based on [Official Ubuntu Docker Image](https://hub.docker.com/_/ubuntu/) with some minor hack:

  - Packaging by Packer Docker builder and Ansible provisioner in single layer
  - Handle `ENTRYPOINT` with [catatonit](https://github.com/openSUSE/catatonit)

### Quick Start

Start Chrony:

    # Pull latest image
    docker pull alvistack/chrony-3.5
    
    # Run as detach
    docker run \
        -itd \
        --cap-add SYS_TIME \
        --name chrony \
        --publish 123:123/udp \
        alvistack/chrony-3.5
    
    # Run with custom /etc/chrony/chrony.conf
    docker run \
        -itd \
        --cap-add SYS_TIME \
        --name chrony \
        --publish 123:123/udp \
        --volume /etc/chrony/chrony.conf:/etc/chrony/chrony.conf \
        alvistack/chrony-3.5

**Success**. Chrony is now available on port `123/udp`.

## Versioning

### `YYYYMMDD.Y.Z`

Release tags could be find from [GitHub Release](https://github.com/alvistack/docker-chrony/releases) of this repository. Thus using these tags will ensure you are running the most up to date stable version of this image.

### `YYYYMMDD.0.0`

Version tags ended with `.0.0` are rolling release rebuild by [GitLab pipeline](https://gitlab.com/alvistack/docker-chrony/-/pipelines) in weekly basis. Thus using these tags will ensure you are running the latest packages provided by the base image project.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
