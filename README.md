# Portefaix Hyperkube

* Master :
[![Circle CI](https://circleci.com/gh/portefaix/hyperkube/tree/master.svg?style=svg)](https://circleci.com/gh/portefaix/hyperkube/tree/master)

* Develop :
[![Circle CI](https://circleci.com/gh/portefaix/hyperkube/tree/develop.svg?style=svg)](https://circleci.com/gh/portefaix/hyperkube/tree/develop)

![logo](https://pkgs.alpinelinux.org/assets/alpinelinux-logo.svg)

[Alpine Linux][] is a Linux distribution built around musl libc and BusyBox.
This image is based on the official Alpine Linux.

This image could be used for running [Kubernetes][] as Docker containers.
We use the all-in-one binary `hyperkube`, which includes `apiserver`, `controller-manager`, `scheduler`, `kubelet` and `kube-proxy`.

## Usage

Install [Docker Compose][] and launch a local [Kubernetes][] cluster :

    $ ./docker-compose --verbose up

## Supported tags

- `1.1.3` [![](https://badge.imagelayers.io/portefaix/hyperkube:1.1.3.svg)](https://imagelayers.io/?images=portefaix/hyperkube:1.1.3 'imagelayers.io')
- `1.0.7` [![](https://badge.imagelayers.io/portefaix/hyperkube:1.0.7.svg)](https://imagelayers.io/?images=portefaix/hyperkube:1.0.7 'imagelayers.io')
- `1.0.1` [![](https://badge.imagelayers.io/portefaix/hyperkube:1.0.1.svg)](https://imagelayers.io/?images=portefaix/hyperkube:1.0.1 'imagelayers.io')


## Development

### Release

The current version is calculated from the script:

    $ wget -q -O- https://storage.googleapis.com/kubernetes-release/release/latest.txt


## License

See [LICENSE](LICENSE) for the complete license.


## Changelog

A [ChangeLog.md](ChangeLog.md) is available.


## Contact

Nicolas Lamirault <nicolas.lamirault@gmail.com>


[Alpine Linux]: http://www.alpinelinux.org

[Kubernetes]: https://github.com/kubernetes/kubernetes
[Docker Compose]: https://github.com/docker/compose
