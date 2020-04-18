
# Installing minikube

## Step 1: Update system
### Run the following commands to update all system packages to the latest release:
```shell
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get upgrade
```

## Step 2: Install KVM or VirtualBox Hypervisor
### For VirtualBox users, install VirtualBox using:
```shell
$ wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
$ wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
$ sudo apt update
$ sudo apt install virtualbox-6.0
```

## Step 3: Download minikube
### download the minikube binary:
```shell
		$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
		$ chmod +x minikube
		$ sudo mkdir -p /usr/local/bin/
		$ sudo install minikube /usr/local/bin/
```
### Confirm version installed:
```shell
$ minikube version
```
