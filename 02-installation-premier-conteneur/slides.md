%title: PODMAN
%author: xavki


# PODMAN : INSTALLATION && Premier conteneur

<br>

* installation 

```
cat /etc/os-release
wget https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/Debian_11/Release.key
cat Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/libcontainers.gpg  >/dev/null
ls
echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/Debian_11/ /" | sudo tee /etc/apt/sources.list.d/libcontainers.list
echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/Debian_11/ /" | sudo tee /etc/apt/sources.list.d/libcontainers.list
sudo apt update
sudo apt install podman
```

Note : peut se faire directement sans ajout de dépôt

-------------------------------------------------------------------------------

# PODMAN : INSTALLATION && Premier conteneur

<br>

* version

```
podman --version
podman info
```

-------------------------------------------------------------------------------

# PODMAN : INSTALLATION && Premier conteneur

<br>

* si warning

```
systemctl --user status dbus.socket
systemctl --user enable --now dbus.socket
systemctl --user status dbus.socket
```

-------------------------------------------------------------------------------

# PODMAN : INSTALLATION && Premier conteneur

<br>

* lister les conteneurs présents

```
podman ps
podman ps -a
podman ps --help
```

-------------------------------------------------------------------------------

# PODMAN : INSTALLATION && Premier conteneur

<br>

* créer un conteneur

```
podman create --name c1 docker.io/busybox
```

-------------------------------------------------------------------------------

# PODMAN : INSTALLATION && Premier conteneur

<br>

* démarrer/stopper un conteneur

```
podman start c1
ps aux
podman stop c1
```

-------------------------------------------------------------------------------

# PODMAN : INSTALLATION && Premier conteneur

<br>

* supprimer un conteneur

```
podman rm c1
```
