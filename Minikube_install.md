**Minikube installation steps**
```
sudo apt update
sudo apt -y install docker.io
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && chmod +x ./kubectl && sudo mv ./kubectl /usr/local/bin/kubectl
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
sudo su
apt install conntrack
sudo usermod -aG docker $USER && newgrp docker
minikube start --driver=docker
```
**To check minikube version on Ubuntu**
```
minikube version
```
**To Check the status of Minikube**
```
minikube status
```
**To install Kubectl**
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x ./kubectl
sudo mv kubectl /usr/local/bin/
kubectl version --client --output=yaml
```
