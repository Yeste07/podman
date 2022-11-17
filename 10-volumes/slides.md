%title: PODMAN
%author: xavki


# PODMAN : Les Volumes

<br>

* Comment persister des données avec podman ?? Volumes

* volumes = création d'un montage entre le host et le conteneur

-----------------------------------------------------------

# PODMAN : Les Volumes

<br>

* création d'un volume

```
podman volume ls
podman volume create xavki
podman volume inspect xavki
```

-----------------------------------------------------------

# PODMAN : Les Volumes

<br>

* ajout de données via le host

```
echo "Xavki" >
$HOME/.local/share/containers/storage/volumes/xavki/_data/salut.txt
```

-----------------------------------------------------------

# PODMAN : Les Volumes

<br>

* ajout des volumes au lancement

```
podman run --rm --name c1 -ti -v xavki:/tmp debian:latest bash
cat /tmp/salut.txt
echo merci > /tmp/xavki.txt
podman ps -a
ls -la $HOME/.local/share/containers/storage/volumes/xavki/_data/
```

Note : on est dans la home !!!

-----------------------------------------------------------

# PODMAN : Les Volumes

<br>

* ajout d'un deuxième conteneur

```
podman run --rm --name c1 -ti -v xavki:/tmp debian:latest bash
```

-----------------------------------------------------------

# PODMAN : Les Volumes

<br>

* volume personnalisé

```
mkdir data
podman run --rm --name c2 -ti -v $PWD/data/:/tmp debian:latest bash
```

-----------------------------------------------------------

# PODMAN : Les Volumes

<br>

CAS ROOT

* création d'un volume en tant que root

```
podman volume create root_xavki
podman volume inspect root_xavki
```
