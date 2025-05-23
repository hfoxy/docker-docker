<p align="center"><a href="https://github.com/crazy-max/docker-docker" target="_blank"><img height="128" src="https://raw.githubusercontent.com/crazy-max/docker-docker/master/.github/docker-docker.jpg"></a></p>

<p align="center">
  <a href="https://github.com/crazy-max/docker-docker/actions?workflow=build"><img src="https://img.shields.io/github/actions/workflow/status/crazy-max/docker-docker/build.yml?branch=master&label=build&logo=github&style=flat-square" alt="Build Status"></a>
  <a href="https://hub.docker.com/r/crazymax/docker/"><img src="https://img.shields.io/docker/stars/crazymax/docker.svg?style=flat-square&logo=docker" alt="Docker Stars"></a>
  <a href="https://hub.docker.com/r/crazymax/docker/"><img src="https://img.shields.io/docker/pulls/crazymax/docker.svg?style=flat-square&logo=docker" alt="Docker Pulls"></a>
  <br /><a href="https://github.com/sponsors/crazy-max"><img src="https://img.shields.io/badge/sponsor-crazy--max-181717.svg?logo=github&style=flat-square" alt="Become a sponsor"></a>
  <a href="https://www.paypal.me/crazyws"><img src="https://img.shields.io/badge/donate-paypal-00457c.svg?logo=paypal&style=flat-square" alt="Donate Paypal"></a>
</p>

## ⚠️ Abandoned project

This project is not maintained anymore and is abandoned. Feel free to fork and
make your own changes if needed.

## About

[Docker](https://www.docker.com/) in Docker (DinD) image inspired by the
[official Docker image](https://github.com/docker-library/docker/).

> [!TIP] 
> Want to be notified of new releases? Check out 🔔 [Diun (Docker Image Update Notifier)](https://github.com/crazy-max/diun)
> project!

___


* [Features](#features)
* [Build locally](#build-locally)
* [Image](#image)
* [Contributing](#contributing)
* [License](#license)

## Features

* [BuildKit](https://github.com/moby/buildkit)
* [binfmt](https://github.com/tonistiigi/binfmt#buildkit-target) (for BuildKit's automatic emulation support)
* [buildx](https://github.com/docker/buildx)
* [Compose](https://github.com/docker/compose) (v2 and v1)
* [CNI plugins](https://github.com/containernetworking/plugins) (for BuildKit)

## Build locally

```shell
git clone https://github.com/crazy-max/docker-docker.git
cd docker-docker

# Build image and output to docker (default)
docker buildx bake

# Build multi-platform image
docker buildx bake image-all
```

## Image

| Registry                                                                                          | Image                           |
|---------------------------------------------------------------------------------------------------|---------------------------------|
| [Docker Hub](https://hub.docker.com/r/crazymax/docker/)                                           | `crazymax/docker`               |
| [GitHub Container Registry](https://github.com/users/crazy-max/packages/container/package/docker) | `ghcr.io/crazy-max/docker`      |

Following platforms for this image are available:

```
$ docker buildx imagetools inspect crazymax/docker --format "{{json .Manifest}}" | \
  jq -r '.manifests[] | select(.platform.os != null and .platform.os != "unknown") | .platform | "\(.os)/\(.architecture)\(if .variant then "/" + .variant else "" end)"'

linux/amd64
linux/arm/v7
linux/arm64
```

## Contributing

Want to contribute? Awesome! The most basic way to show your support is to star
the project, or to raise issues. You can also support this project by [**becoming a sponsor on GitHub**](https://github.com/sponsors/crazy-max)
or by making a [PayPal donation](https://www.paypal.me/crazyws) to ensure this
journey continues indefinitely!

Thanks again for your support, it is much appreciated! :pray:

## License

MIT. See `LICENSE` for more details.
