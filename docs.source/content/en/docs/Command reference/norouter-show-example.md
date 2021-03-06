---
title: "norouter show-example"
linkTitle: "norouter show-example"
weight: 40
---

`norouter show-example`  (`norouter show-ex`) shows an example manifest.

## Examples

```console
$ norouter show-example
# Example manifest for NoRouter.
# Run `norouter <FILE>` to start NoRouter with the specified manifest file.
#
# The `norouter` binary needs to be installed on all the remote hosts.
# Run `norouter show-installer` to show the installation script.
#
hosts:
# localhost
  local:
    vip: "127.0.42.100"
# Docker & Podman container (docker exec, podman exec)
# The cmd string can be also written as a string slice: ["docker", "exec", "-i", "some-container", "norouter"]
  docker:
    cmd: "docker exec -i some-container norouter"
    vip: "127.0.42.101"
    ports: ["8080:127.0.0.1:80"]
# Kubernetes Pod (kubectl exec)
  kube:
    cmd: "kubectl --context=some-context exec -i some-pod -- norouter"
    vip: "127.0.42.102"
    ports: ["8080:127.0.0.1:80"]
# LXD container (lxc exec)
  lxd:
    cmd: "lxc exec some-container -- norouter"
    vip: "127.0.42.103"
    ports: ["8080:127.0.0.1:80"]
# SSH
# If your key has a passphrase, make sure to configure ssh-agent so that NoRouter can login to the remote host automatically.
  ssh:
    cmd: "ssh some-user@some-ssh-host.example.com -- norouter"
    vip: "127.0.42.104"
    ports: ["8080:127.0.0.1:80"]
```

## norouter show-example --help
```
NAME:
   norouter show-example - show an example manifest

USAGE:
   norouter show-example [command options] [arguments...]

OPTIONS:
   --help, -h  show help (default: false)
```
