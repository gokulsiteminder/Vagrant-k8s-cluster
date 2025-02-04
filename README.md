# Vagrant-k8s-cluster

This installs a test Kubernetes cluster in [vagrant](http://vagrantup.com/) using [virtualbox](https://www.virtualbox.org/) hosts..

## Requirements

* [Vagrant](http://vagrantup.com/)
* [Virtualbox](https://www.virtualbox.org/)
* [yq](http://mikefarah.github.io/yq/)
* [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Setup

You can setup the cluster and kubectl context using the `setup.sh` script. This configures 1 Master node and 3 Worker nodes. You can change the number of worker nodes in `Vagrantfile` by updating the value of `NODE_COUNT`.

```
$ ./setup.sh -h
Kubernetes cluster setup on vagrant.

Usage:
    setup.sh [-h|--help] [-n|--networking <flannel|calico|canal|weavenet>] [-c|--host-count <n>]

Arguments:
    -h|--help                                             Print usage
    -n|--networking <flannel|calico|canal|weavenet>       Kubernetes networking model to use [Default: flannel]
    -c|--host-count <n>                                   Number of worker nodes [Default: 2]

Examples:
    ./setup.sh
    ./setup.sh -n calico
    ./setup.sh -n weavenet -c 3

```

## Destroy

You can destroy the cluster and kubectl config using `destroy.sh` script.

```
$ sh destroy.sh
```
