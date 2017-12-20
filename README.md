[![CircleCI](https://circleci.com/gh/bitnami/bitnami-docker-swift/tree/master.svg?style=shield)](https://circleci.com/gh/bitnami/bitnami-docker-swift/tree/master)
[![Slack](http://slack.oss.bitnami.com/badge.svg)](http://slack.oss.bitnami.com)

# Bitnami Swift Development Container

## TL;DR;

### Local workspace

```bash
$ mkdir ~/myapp && cd ~/myapp
$ curl -LO https://raw.githubusercontent.com/bitnami/bitnami-docker-swift/master/docker-compose.yml
$ docker-compose up
```

## Why use Bitnami Images?

* Bitnami closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Bitnami images the latest bug fixes and features are available as soon as possible.
* Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* Bitnami images are built on CircleCI and automatically pushed to the Docker Hub.
* All our images are based on [minideb](https://github.com/bitnami/minideb) a minimalist Debian based container image which gives you a small base container image and the familiarity of a leading linux distribution.

## Introduction

[Swift](https://www.swift.org/) is a general-purpose programming language built using a modern approach to safety, performance, and software design patterns.

The Bitnami Swift Development Container has been carefully engineered to provide you and your team with a highly reproducible Swift development environment. We hope you find the Bitnami Swift Development Container useful in your quest for world domination. Happy hacking!

[Learn more about Bitnami Development Containers.](https://docs.bitnami.com/containers/how-to/use-bitnami-development-containers/)

## Getting started

The quickest way to get started with the Bitnami Swift Development Container is using [docker-compose](https://docs.docker.com/compose/).

Begin by creating a directory for your Swift application:

```bash
mkdir ~/myapp
cd ~/myapp
```

Download the [docker-compose.yml](https://raw.githubusercontent.com/bitnami/bitnami-docker-swift/master/docker-compose.yml) file in the application directory:

```bash
$ curl -LO https://raw.githubusercontent.com/bitnami/bitnami-docker-swift/master/docker-compose.yml
```

Next, launch the Swift application development environment using:

```bash
$ docker-compose up
```

The above command creates a container service for Swift development and bootstraps a new Swift application, named `myapp` in working directory. You can use your favorite IDE for developing the application.

## Executing commands

Commands can be launched inside the `myapp` Swift Development Container with `docker-compose` using the [exec](https://docs.docker.com/compose/reference/exec/) command.

> **Note**:
>
> The `exec` command was added to `docker-compose` in release [1.7.0](https://github.com/docker/compose/blob/master/CHANGELOG.md#170-2016-04-13). Please ensure that you're using `docker-compose` version `1.7.0` or higher.

The general structure of the `exec` command is:

```bash
$ docker-compose exec <service> <command>
```

, where `<service>` is the name of the container service as described in the `docker-compose.yml` file and `<command>` is the command you want to launch inside the service.

To see the Swift version currently installed:

```bash
$ docker-compose run myapp swift --version
```

You can create your swift project:

```bash
$ docker-compose run myapp mkdir yourapp
$ docker-compose run myapp swift package init --type executable -C yourapp
```

Then you can develop your swift code and when your app is ready to be build you can execute:

```bash
$ docker-compose run myapp swift build -C yourapp
```

Finally you can execute your app:

```bash
$ docker-compose run myapp yourapp/.build/debug/yourapp
```

## Issues

If you encountered a problem running this container, you can file an [issue](../../issues/new). For us to provide better support, be sure to include the following information in your issue:

- Host OS and version (`uname -a`)
- Docker version (`docker version`)
- Docker info (`docker info`)
- Docker image version (`echo $BITNAMI_IMAGE_VERSION` inside the container)
- Steps to reproduce the issue.

## Community

Most real time communication happens in the `#containers` channel at [bitnami-oss.slack.com](http://bitnami-oss.slack.com); you can sign up at [slack.oss.bitnami.com](http://slack.oss.bitnami.com).

Discussions are archived at [bitnami-oss.slackarchive.io](https://bitnami-oss.slackarchive.io).

## License

Copyright (c) 2015-2017 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
