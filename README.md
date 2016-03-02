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


