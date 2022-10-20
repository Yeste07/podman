%title: PODMAN
%author: xavki


# PODMAN : Intéragir - Attach vs Exec 

<br>

Définitions :

	* conteneur : processus actif (PID) et isolé (ressources, user...)

	* image : code et environnement du processus (stockage et partage)

----------------------------------------------------------------------

# PODMAN : Intéragir - Attach vs Exec 

<br>

* Comment "entrer" dans un conteneur existant ?

		podman exec vs podman attach

	* exec = deuxième conteneur avec le même env/namespaces...

	* attach = atatchement au processus existant 

----------------------------------------------------------------------

# PODMAN : Intéragir - Attach vs Exec 

<br>

* Exec : exemple

```
podman ps
podman run -ti --name c1 debian:latest bash
podman exec -ti c1 bash
ps fauxwww
```

Note : run en arrière plan -d

----------------------------------------------------------------------

# PODMAN : Intéragir - Attach vs Exec 

<br>

* Attention : sortir d'un attach

```
Ctrl-P / Ctrl-Q
```
