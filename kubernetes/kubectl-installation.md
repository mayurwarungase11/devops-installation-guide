# EKS Cluster Setup

# Install eksctl CLI tool for creating EKS Clusters on AWS

```bash
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
```

```bash
sudo mv /tmp/eksctl /usr/local/bin
```

```bash
eksctl version
```

# Install kubectl

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

```bash
chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl
```

```bash
kubectl version --client
```
# Create Amazon EKS cluster using eksctl

```bash
eksctl create cluster --name RedHat11 --region ap-south-1 --version 1.32 --nodegroup-name linux-nodes --node-type m7i-flex.large --nodes 2
```
# Log In Into EKS cluster

```bash
aws eks update-kubeconfig --name RedHat11
```

# Delete EKS Cluster

```bash
eksctl delete cluster --name RedHat11 --region ap-south-1
```
