## Step 1: Install Docker

### Set up the repository
1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:
```shell
sudo apt update
```
```shell
sudo apt install ca-certificates curl gnupg lsb-release
```
2. Add Docker’s official GPG key:
```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
3. Use the following command to set up the stable repository. 
```shell
 echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Install Docker Engine
1. Update the apt package index, and install the latest version of Docker Engine and containerd:
```shell
sudo apt update
```
```shell
sudo apt install docker-ce docker-ce-cli containerd.io
```
2. Add your user to the 'docker' group. 
```shell
sudo usermod -aG docker $USER && newgrp docker
```

## Step 2: Install kubectl using native package management
1. Download the Google Cloud public signing key.
```shell
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
```
2. Add the Kubernetes apt repository.
```shell
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```
3. Update apt package index with the new repository and install kubectl.
```shell
sudo apt update
```
```shell
sudo install kubectl
```

## Step 3: Install Helm from script
1. Download and run the installer script to install Helm
```shell
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
```
```shell
chmod 700 get_helm.sh
```
```shell
./get_helm.sh
```

## Step 4: Install Minikube
1. Download Minikube as a static binary
```shell
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube
```
```shell
sudo cp minikube /usr/local/bin && rm minikube
```
2. Move the Minikube binary to your _/usr/local/bin_ location.
```shell
sudo cp minikube /usr/local/bin && rm minikube
```