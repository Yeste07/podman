%title: PODMAN
%author: xavki


# PODMAN : INTRODUCTION




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


https://www.redhat.com/sysadmin/image-stores-podman

https://devopscube.com/podman-tutorial-beginners/

* migration
sudo podman container checkpoint <container_id> -e /tmp/checkpoint.tar.gz
scp /tmp/checkpoint.tar.gz <destination_system>:/tmp
sudo podman container restore -i /tmp/checkpoint.tar.gz


podman --runtime crun run -it docker.io/busybox


podman port -l

/etc/containers/registries.conf.d/shortnames.conf

/etc/containers/registries.conf
[registries.search]
registries = ['docker.io']

$HOME/.config/containers/registries.conf


https://github.com/rootless-containers/slirp4netns
ip netns list



https://devopscube.com/podman-tutorial-beginners/


https://docs.podman.io/en/latest/markdown/podman-generate-systemd.1.html
