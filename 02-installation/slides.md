%title: PODMAN
%author: xavki


# PODMAN : INTRODUCTION


<br>

* Podman supporté Redhat

* Remplaçant à la CLI Docker

* utilisation rootless (maintenant arrivé sur docker)

* introduction de la notion de pods (hors kubernetes)

* reprise des manifestes kubernetes

* reprise de la CLI de docker strictement

```
alias docker='podman'
```

Docker vs Podman :

	* Docker CLI > Docker Engine > ContainerD > RunC>  Kernel

	* Podman > RunC > Kernel

Sites: 

https://podman.io/
https://docs.podman.io/
https://github.com/containers
https://github.com/containers/podman
https://github.com/containers/podman-desktop

* si warning

```
systemctl --user status dbus.socket
systemctl --user enable --now dbus.socket
systemctl --user status dbus.socket
```


podman run --name c1 -it docker.io/busybox
podman generate kube c1 > c1.yaml
podman play kube c1.yaml

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

podman login docker.io

podman container checkpoint <container_id>

podman container restore <container_id>


* migration
sudo podman container checkpoint <container_id> -e /tmp/checkpoint.tar.gz
scp /tmp/checkpoint.tar.gz <destination_system>:/tmp
sudo podman container restore -i /tmp/checkpoint.tar.gz


podman --runtime crun run -it docker.io/busybox


podman  run --name docker-nginx -p 8080:80 docker.io/nginx
podman port -l

/etc/containers/registries.conf.d/shortnames.conf

/etc/containers/registries.conf
[registries.search]
registries = ['docker.io']

$HOME/.config/containers/registries.conf


https://devopscube.com/podman-tutorial-beginners/
