# Conteneurisation-Docker

## TP1 conteneurisation et orchestration


### Installation de docker et docker-compose via un script bash

https://docs.docker.com/engine/install/ubuntu/
https://docs.docker.com/compose/install/linux/

```
#!/bin/bash

#######################
##Install docker
sudo apt-get remove docker docker-engine docker.io containerd runc
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

########################
##Install docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

### Commandes à tester
```
docker run hello-world
```
![](https://i.imgur.com/6abfUSl.png)

```
docker run -it ubuntu bash
```
![](https://i.imgur.com/8svtVna.png)

```
docker images
```
![](https://i.imgur.com/1zZTurU.png)

```
docker ps -a
```
![](https://i.imgur.com/DklFqCT.png)

```
docker run -p 80:80 nginx
```
![](https://i.imgur.com/d5kDTV8.png)
![](https://i.imgur.com/S2kHuWu.png)

```
docker run -d -p 80:80 nginx
```
![](https://i.imgur.com/xSqxjst.png)

![](https://i.imgur.com/DOfL9aJ.png)

