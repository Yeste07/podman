%title: PODMAN
%author: xavki


# PODMAN : INTRODUCTION


podman save -o nginx.tar docker.io/library/nginx:latest
podman load -i nginx.tar

podman volume create foss_volume
podman volume inspect foss_volume

```
echo "Hello from the third dimension! I am your HOST" >> /home/username/.local/share/containers/storage/volumes/foss_volume/_data/host.txt
```

podman export -o fosslinux_fedora_001.tar db5dda4753c0
podman import fosslinux_fedora_001.tar fosslinux_fedora_imported

podman inspect --format='{{.State.StartedAt}}' db5dda4753c0

podman kill --signal="SIGHUP" a3290c9b553b

podman run --name c1 -it docker.io/busybox
podman generate kube c1 > c1.yaml
podman play kube c1.yaml
podman ps -a --pod
podman pod top fosslinux_001_pod
podman pod stats -a –no-stream
podman pod inspect fosslinux_001_pod
podman pod stop fosslinux_001_pod
podman pod rm fosslinux_001_pod


podman run -dt --name health_check_001 -p 8080:8080 --health-cmd='curl http://localhost:8080 || exit 1' --health-interval=0 registry.access.redhat.com/ubi8/httpd-24
podman healthcheck run health_check_001

podman system df
podman system info
podman system prune

podman events
podman events --filter event=restore
podman events --filter event=push



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


mkdir -p $HOME/.config/systemd/user/ 
cd $HOME/.config/systemd/user
podman generate systemd --files --name --new myblog

sudo loginctl enable-linger username

https://www.redhat.com/sysadmin/image-stores-podman

https://devopscube.com/podman-tutorial-beginners/



podman --runtime crun run -it docker.io/busybox


podman port -l

/etc/containers/registries.conf.d/shortnames.conf



https://github.com/rootless-containers/slirp4netns
ip netns list



https://devopscube.com/podman-tutorial-beginners/


https://docs.podman.io/en/latest/markdown/podman-generate-systemd.1.html
