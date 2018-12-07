# docker-local-registry-cli
A script for getting list and remove repository from docker local registry 

## How to use
Edit [script](#docker-registry) and set registry address:

```bash
registry=<address>
```
get repositories list:

```bash
$docker-registry ls
```
remove repository:

```bash
$docker-registry rm <repo name>
```

## Requirement

```bash
pip install requests
```
