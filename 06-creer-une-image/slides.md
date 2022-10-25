%title: PODMAN
%author: xavki


# PODMAN : Créer une image

<br>

Deux manières de créer une image :
	* commit d'un conteneur existant
	* Dockerfile

<br>

Les images sont constituées de couches = layers
	* prochaines vidéos

------------------------------------------------------------------

# PODMAN : Créer une image

<br>

COMMIT

<br>

* lancer un conteneur

```
podman run -d --name c2 debian:bullseye-slim sleep infinity
podman exec -ti c2 bash
podman exec -ti c2 touch /titi
```

* utilisation de la commande commit

```
podman commit c2 mydeb:v1
```

------------------------------------------------------------------

# PODMAN : Créer une image

<br>

DOCKERFILE

<br>

* Dockerfile avec syntax spécifique

```
FROM docker.io/debian:bullseye-slim
RUN apt update
RUN apt install -y git
RUN apt clean
RUN rm -rf /var/lib/apt/lists/*
```

------------------------------------------------------------------

# PODMAN : Créer une image

<br>

* lancer un build

```
podman build -t mydebian:v0.2 .
```

Note : 
	* . => Dockerfile
	* --file (-f)

------------------------------------------------------------------

# PODMAN : Créer une image

<br>

* quelques options

--format
BUILDAH_FORMAT


--squash-all
--no-cache
--from
--build-context
--dns-option
--env
