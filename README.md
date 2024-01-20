# Credits 

Mise à jour de https://github.com/cnadal/machine_docker aujourd'hui obsolète  

# Description 

**Testé sous DEBIAN 10 et ubuntu 23.04**

L'objectif de ce projet et de pouvoir commencer un projet web localement et rapidement avec un ensemble d'outils et de dépendances pré-installés. En exploitant la technologie de containerisation Docker. 

# Containers 

- PHP 8.0.13 
- MYSQL 8.0.32
- PHPMYADMIN

# Installation 

Prêt à l'emploi pour des projets Symfony v6.0.x : 

1) apt install git sudo
2) git clone https://github.com/adriraxor/docker_adriraxor.git
3) chmod 755 ./get-docker.sh 
4) ./get-docker.sh
5) chmod 755 ./install-docker-compose
6) ./install-docker-compose 
7) /!\ nano .env (configuration par défaut) /!\
8) docker-compose build
9) docker-compose up -d

# Pour RaspyOS

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

