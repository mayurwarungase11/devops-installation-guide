# Terraform Installation

# Update packages

```bash
sudo apt-get update
```
# Install required tools
```bash
sudo apt-get install -y gnupg software-properties-common curl
```

# Add HashiCorp GPG key

```bash
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -

```

# Add the HashiCorp repo

```bash
sudo apt-add-repository "deb https://apt.releases.hashicorp.com $(lsb_release -cs) main"
```

# Update again

```bash
sudo apt-get update
```

# Install Terraform

```bash
sudo apt-get install terraform
```

## Verify

```bash
terraform version
```
