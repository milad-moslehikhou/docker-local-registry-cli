# docker-local-registry-cli
This script returns list and removes repository from docker local registry.

## How to use
Edit [script](/docker-registry) and set registry address:

```bash
registry=<address>
```
Getting repositories list:

```bash
$docker-registry ls
```
Removing repository:

```bash
$docker-registry rm <repo name>
```
## Important
For deleting files on host completely, You should set `REGISTRY_STORAGE_DELETE_ENABLED=True` when running registry container

```bash
$docker container run -d -p 5000:5000 --restart=always -e REGISTRY_STORAGE_DELETE_ENABLED=True registry
```
And after removing repository (`docker-registry rm <repo name>`) run below command on host

```bash
$docker container exec <registry container name or id>  bin/registry garbage-collect  /etc/docker/registry/config.yml
```

## Requirement

```bash
$pip install requests
```
