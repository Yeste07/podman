%title: PODMAN
%author: xavki


# PODMAN : INTRODUCTION


<br>

* management de conteneurs

* Podman = Pod Manager

* première release en 2018 (docker 2013)

* OCI compatible 

https://github.com/opencontainers/image-spec

---------------------------------------------------------------------------

# PODMAN : INTRODUCTION

<br>

* Podman supporté Redhat

* au début debug pour CRI-O

* sans daemon (directement RunC) donc par de root

* langage : Golang

* compatible : Ubuntu, Fedora, CentOS, Debian, OpenSuse et RHEL
	client sur MacOS et Windows

---------------------------------------------------------------------------

# PODMAN : INTRODUCTION

<br>

* Remplaçant à une partie CLI/Engine Docker

<br>

* utilisation rootless (maintenant arrivé sur docker)

<br>

* introduction de la notion de pods (hors kubernetes)

<br>

* reprise des manifestes kubernetes

<br>

* reprise de la CLI de docker strictement

```
alias docker='podman'
```
-----------------------------------------------------------------------------

# PODMAN : INTRODUCTION

<br>

Docker vs Podman :

	* Docker CLI > Docker Engine > ContainerD > RunC>  Kernel

	* Podman > RunC > Kernel

---------------------------------------------------------------------------

# PODMAN : INTRODUCTION

<br>

Sites: 

https://podman.io/
https://docs.podman.io/
https://github.com/containers
https://github.com/containers/podman
https://github.com/containers/podman-desktop

<br>

podman run --name c1 -it docker.io/busybox
podman generate kube c1 > c1.yaml
podman play kube c1.yaml

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: webserver
    image: docker.io/nginx:latest
    ports:
    - containerPort: 80
```

---------------------------------------------------------------------------

# PODMAN : INTRODUCTION

<br>

Fonctionnalités

	* cli identique à docker

	* pods (multicontainers, hostname...)

	* endpoints

	* générateur manifests pods

	* accès distant

	* choix du container runtime (RunC, Crun)

---------------------------------------------------------------------------

# PODMAN : INTRODUCTION

<br>

Existe podman-compose : 
https://github.com/containers/podman-compose
