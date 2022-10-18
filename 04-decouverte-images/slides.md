%title: PODMAN
%author: xavki


# PODMAN : Découvertes des Images

<br>

Définitions :

	* conteneur : processus actif (PID) et isolé (ressources, user...)

	* image : code et environnement du processus (stockage et partage)

<br>

* lister les images présentes localement

```
podman image ls
podman image ls --noheading
podman image ls -q
podman images
```

-------------------------------------------------------------------

# PODMAN : Découvertes des Images

<br>

* formats de sortie et filtres

```
podman images --format "table {{.ID}} {{.Repository}} {{.Tag}}"
podman images --format json
podman images --filter dangling=true
podman images --sort repository
```

Note : dangling coorespond à une image sans nom (build local)

-------------------------------------------------------------------

# PODMAN : Découvertes des Images

<br>

* chercher une image

```
podman search nginx
cat /etc/containers/registries.conf
cat $HOME/.config/containers/registries.conf
```

-------------------------------------------------------------------

# PODMAN : Découvertes des Images

<br>

* puller une image

```
podman pull nginx
```

<br>

* supprimer une image

```
podman image rm xxxxx
podman rmi xxx
```

<br>

* où est-elle stockée ?

```
podman info
```

Attention : rootful / rootless

-------------------------------------------------------------------

# PODMAN : Découvertes des Images

<br>

* si besoin de se connecter à un hub

```
podman login docker.io
```

-------------------------------------------------------------------

# PODMAN : Découvertes des Images

<br>

* historique de construction d'une image

```
podman history docker.io/library/nginx
--no-trunc --format "table{{.ID}}, {{.CreatedBy}}"
```
