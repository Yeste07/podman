%title: PODMAN
%author: xavki


# PODMAN : Push, Pull & Registry

<br>

* Recherche d'images

```
podman search nginx
```

----------------------------------------------

# PODMAN : Push, Pull & Registry

<br>

* Les registries

https://quay.io/
https://hub.docker.com/

Actions :

	* pull

	* push

----------------------------------------------

# PODMAN : Push, Pull & Registry

<br>

* Configuration /etc/containers/registries.conf

```
unqualified-search-registries = ["registry.fedoraproject.org", "registry.access.redhat.com", "docker.io", "quay.io"]
```

----------------------------------------------

# PODMAN : Push, Pull & Registry

<br>

* Configuration personnalisé par user ;)

vim $HOME/.config/containers/registries.conf

```
unqualified-search-registries = ["quay.io"]
``` 

----------------------------------------------

# PODMAN : Push, Pull & Registry

<br>

* Metadata d'images

```
ls .local/share/containers/storage/vfs-images/
```

----------------------------------------------

# PODMAN : Push, Pull & Registry

<br>

* stockage root vs user

```
/var/lib/containers/storage
$HOME/.local/share/containers/storage/
```

----------------------------------------------

# PODMAN : Push, Pull & Registry

<br>

Pousser une image vers une registry

* connexion à la registry

```
podman login docker.io
```

<br>

* build de l'image en intégrant le chemin

```
podman push docker.io/priximmo/p1:v0.1
```




