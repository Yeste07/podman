%title: PODMAN
%author: xavki


# PODMAN : Images - Les Layers

<br>

Deux manières de créer une image :
	* commit d'un conteneur existant
	* Dockerfile ou Containerfile


----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

Une image constituée de couches (layers) :

	* lecture seule = image (inactif)

	* lecture écriture = conteneur (actif)

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

Les layers sont symbolisés par un sha256

<br>

* image simplifée = lecture seule

```
	Image 1  |  Image 2

	Layer 4  |  Layer Z
	Layer 3  |  Layer F
	Layer 1  |  Layer A
```

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

* les layers sont partagés si identiques (cache)

```
	Image 1  |  Image 2

	Layer 4  |  Layer Z
	Layer 3  |  Layer F
				Layer2
	Layer 1  |  Layer A
```

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

* et on lance un conteneur

```
	Conteneur11   |   Conteneur22 
rw	Layer5      |   LayerX


		Image 1  	  |  	Image 2
ro	Layer 4  		|  	Layer Z
ro	Layer 3  		|  	Layer F
ro					Layer2
ro	Layer 1  		|  	Layer A
```

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

* la mauvaise idée

```
FROM docker.io/debian:bullseye-slim
RUN apt update -qq 
RUN apt install -qq -y wget 
RUN apt clean 
RUN rm -rf /var/lib/apt/lists/*
RUN wget http://xcal1.vodafone.co.uk/10MB.zip 
RUN rm -f 10MB.zip
```

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

* la bonne pratique

```
FROM docker.io/debian:bullseye-slim
RUN apt update -qq && apt install -qq -y wget && apt clean && rm -rf /var/lib/apt/lists/*
RUN wget http://xcal1.vodafone.co.uk/10MB.zip && rm -f 10MB.zip
```

Note : attention si un layer = plus de cache :)

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

* l'historique d'une image

```
docker history --no-trunc monimage:maversion
docker history xavki:v1.0 --format "{{.ID}}\t{{.CreatedBy}}"
```

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

```
docker diff test
```

----------------------------------------------------------------------------

# PODMAN : Images - Les Layers

<br>

* autre exemple : imaginons un secret ajouté puis supprimé

```
FROM docker.io/debian:bullseye-slim
RUN echo "monsecret" > xavki.txt
RUN rm xavki.txt
```

```
podman history <xxx>
```
