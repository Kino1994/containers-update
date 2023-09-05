# Install for AWS CLI, Docker, Docker Compose, Minikube, Kubectl, Helm, Cloud Foundry

#### AWS:

```sh
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws configure
aws sts get-caller-identity
```

#### Docker:

```
wget https://download.docker.com/linux/static/stable/x86_64/docker-25.0.3.tgz
tar xzvf docker-25.0.3.tgz
for file in /home/joaquin/docker/*; do filename=$(basename "$file"); [ -f "/usr/bin/$filename" ] && sudo rm "/usr/bin/$filename"; done
sudo cp docker/* /usr/bin/
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
sudo dockerd &
```

#### Docker Compose:

```sh
sudo rm /usr/bin/docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/v2.24.6/docker-compose-linux-x86_64" -o /usr/bin/docker-compose
sudo chmod a+rx /usr/bin/docker-compose
```

#### Minkube:
```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/bin/minikube
```

#### Kubectl:

```sh
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
echo "$(<kubectl.sha256) kubectl" | sha256sum --check
sudo install -o root -g root -m 0755 kubectl /usr/bin/kubectl
```

#### Helm:
```sh
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
```

#### Cloud Foundry:
```wget -q -O - https://packages.cloudfoundry.org/debian/cli.cloudfoundry.org.key | sudo apt-key add -
echo "deb https://packages.cloudfoundry.org/debian stable main" | sudo tee /etc/apt/sources.list.d/cloudfoundry-cli.list```

