%title: PODMAN
%author: xavki


# PODMAN : Save & Export

<br>

* une image 

```
FROM debian:bullseye
RUN touch toto
```

--------------------------------------------------

# PODMAN : Save & Export

<br>

IMAGE : save/load

<br>

* export une image en tar

```
podman save -o mytest-v1.0.0.tar localhost/mytest:v1.0.0
podman rmi -a
```

--------------------------------------------------

# PODMAN : Save & Export

<br>

* import une image en tar

```
podman load -i mytest-v1.0.0.tar
```

--------------------------------------------------

# PODMAN : Save & Export

<br>

CONTENEUR : export/import

<br>

* export d'un conteneur sous forme d'image

```
podman run -d --name c1 localhost/mytest:v1.0.0 sleep infinity
podman export -o c1.tar c1
```

--------------------------------------------------

# PODMAN : Save & Export

<br>

* import de l'image du conteneur

```
podman import c1.tar c2
podman run --rm -ti --name c2 localhost/c2 bash
```

