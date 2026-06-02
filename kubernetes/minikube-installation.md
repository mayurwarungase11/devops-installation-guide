
## Minikube Installation on AWS EC2

## Step 1: Create an AWS EC2 instance with Ubuntu 
Instance Type: m7i-flex.large 

## Step 2 : Install Docker
````
Install Docker
# Update package index
sudo apt update -y

# Install required dependencies
sudo apt install -y ca-certificates curl gnupg lsb-release

# Create directory for Docker GPG key
sudo mkdir -p /etc/apt/keyrings

# Add Docker's official GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Add Docker repository
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Refresh package index
sudo apt update -y

# Install Docker Engine
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Verify Docker installation
docker --version

# Start Docker service
sudo systemctl start docker

# Enable Docker service on boot
sudo systemctl enable docker

# Check Docker service status
sudo systemctl status docker

sudo usermod -aG docker $USER
newgrp docker

# Verify
docker ps     


````
## Install kubectl
Download the latest release with the command:
````
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
````

Install kubectl:
````
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
````
Note:
If you do not have root access on the target system, you can still install kubectl to the ~/.local/bin directory:
````
chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl
````
````
kubectl version --client
````
## Step 4: Install Minikube
````
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
````
````
sudo install minikube-linux-amd64 /usr/local/bin/minikube
````
````
minikube start
````
````
minikube stop
````


--------------------------------------------

## $${\color {blue}\textbf {Ingress On Minikube}}$$
````
https://v1-33.docs.kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/
````
