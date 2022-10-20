%title: PODMAN
%author: xavki


# PODMAN : Intéragir - Attach vs Exec 

<br>

Définitions :

	* conteneur : processus actif (PID) et isolé (ressources, user...)

	* image : code et environnement du processus (stockage et partage)

<br>

* Comment "entrer" dans un conteneur existant ?

		podman exec vs podman attach

* exec = création d'un deuxième conteneur avec le même env

```
podman ps
podman run -ti --name c1 debian:latest bash
podman exec -ti c1 bash
```

Note : run en arrière plan -d



<br>

* sortir d'un attach

```
Ctrl-P / Ctrl-Q
```
