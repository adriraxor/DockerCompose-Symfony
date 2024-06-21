# Credits 

Fork de https://github.com/cnadal/machine_docker qui est obsolète

# Description 

L'objectif de ce fork et de pouvoir commencer un projet web symfony rapidement avec un ensemble d'outils et de dépendances pré-installés.

Dans ce fork, plus particulièrement dans le container WEB. NodeJS v20.0.0 est pré-installé dans le container ainsi que la plus récente version du CLI symfony et de PHP.
De plus, le container MySQL est mis à jour à la version la plus récente et la plus stable.   

# Containers 

- PHP 8.0.13 (WEB)
- MYSQL 8.0.32 (DB)
- PHPMYADMIN 

# Installation 

Prêt à l'emploi pour des projets Symfony v6.0.x
NodeJS pré-installé dans le container

1) apt install git sudo
2) git clone https://github.com/adriraxor/docker_adriraxor.git
3) chmod 755 ./get-docker.sh 
4) ./get-docker.sh
5) chmod 755 ./install-docker-compose
6) ./install-docker-compose 
7) /!\ nano .env (configuration par défaut) /!\
8) docker-compose build
9) docker-compose up -d

# Pour RaspyOS - testé sous Raspberry PY 5 8gb RAM

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Ajouter le "repository" aux sources "APT" :
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

