
# Installing minikube and kubctl
> Minikube is an open source tool that was developed to enable developers and system administrators to run a single cluster of Kubernetes on their local machine. Minikube starts a single node kubernetes cluster locally with small resource utilization. This is ideal for development tests and POC purposes.

> Minikube supports Kubernetes features such as:
> 1. DNS
> 2. NodePorts
> 3. ConfigMaps and Secrets
> 4. Dashboards
> 5. Container Runtime: Docker, CRI-O, and containerd
> 6. Enabling CNI (Container Network Interface)
> 7. Ingress
> 8. PersistentVolumes of type hostPath

## Step 1: Update system
##### Run the following commands to update all system packages to the latest release:
```shell
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get upgrade
```

## Step 2: Install KVM or VirtualBox Hypervisor
##### For VirtualBox users, install VirtualBox using:
```shell
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
sudo apt update
sudo apt install virtualbox-6.0
```

## Step 3: Download minikube
##### download and install the minikube binary:
```shell
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube
sudo mkdir -p /usr/local/bin/
sudo install minikube /usr/local/bin/
```
##### Confirm version installed:
```shell
minikube version
```

## Step 4: Install kubectl on Ubuntu / Debian
##### download and install the kubectl binary:
```shell
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.18.0/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
```
##### Confirm version installed:
```shell
kubectl version -o json 
```

## Step 5: Starting minikube
```shell	
minikube start --driver=virtualbox
minikube status
```
		
## Step 6: Minikube Basic operations
##### To check cluster status, run:
```shell
kubectl cluster-info
```
##### To View Config, use:
```shell
kubectl config view
```
##### To check running nodes:
```shell
kubectl get nodes
```
##### Access minikube VM using ssh:
```shell
minikube ssh
```
##### To stop a running local kubernetes cluster, run:
```shell
minikube stop
```
##### To delete a local kubernetes cluster, use:
```shell
minikube delete
```
## Step 7: Enable Kubernetes Dashboard
```shell
minikube addons list
```
##### To open directly on your default browser, use:
```shell
minikube dashboard
```
