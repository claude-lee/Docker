# Docker Project 

This is a simple guide for setting up a docker project on a linux virtual machine


### Download Ubuntu
http://www.ubuntu.com/download/
Select Download -> Server

### Make sure you have Virtualization enabled
Press 'ESC' during start up (or whatever it key it shows during startup) to enter the BIOS settings.
Go to advanced and check 'Virtualization'

### Create a VM with VirtualBox
Open VirtualBox
Select New
Choose a name and select Ubuntu 64 Bit version
In settings -> System -> Acceleration, both boxes should be checked
In settings -> Storage -> Controller IDE -> Empty, select the ios ubuntu image that you downloaded before
In Settings -> Network -> Adapter2, select Host-Only-Adapter
Press START

### Installing Docker on ubuntu
change to sudo user
```
sudo su -
```

check if you have docker installed
```
service docker status
```

Check the kernel version
```
uname -a
```

Sync package index from source
```
apt-get update
```

install docker
```
apt-get install -y docker.io
```

check if you have docker installed now
```
service docker status
```

check the docker version
```
docker -v
```

check docker version (detailed)
```
docker version
```
docker info (images and containers)
```
docker info
```

download gpg
```
wget -qO- https://get.docker.com/gpg | apt-key add -
```
adding docker repo to apt sources
```
echo deb http://get.docker.com/ubuntu docker main > /etc/apt/sources.list.d/docker.list
```

Sync with new repo
```
apt-get update
```

Check latest version
```
apt-get install lxc-docker
```

See docker socket (docker.sock)
```
ls -l /run
```

Exit sudo user
```
exit
```

Fire up a new container
```
docker run -it ubuntu /bin/bash
```

Check if docker group exists
```
cat /etc/group
```
You'll see 'docker:x:112: in the bottom of the group file

Add user (you) to docker group
```
sudo gpasswd -a claudia docker
```

Check group file again
```
cat /etc/group
```
Now you should see 'docker:x:112:claudia'

Change back to root
```
sudo su -
```

start a new container
```
docker run -it ubuntu /bin/bash
```

Ping google
```
ping 8.8.8.8
```

check the running processes
```
ps -elf
```

check our host
```
cat /etc/hosts
```

check our IP
```
ip a
```

List containers (all)
```
docker ps -a
```

List images(all)
```
docker images -a
```
