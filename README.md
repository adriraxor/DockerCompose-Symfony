# Credits 

Mise à jour de https://github.com/cnadal/machine_docker aujourd'hui obsolète  

# Description 

**Testé sous DEBIAN 10**

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

(Note pour la création du wiki) 

--- Installation des dépendances manuellement dans le container WEB si pas installé avec le dockerfile ---

- NodeJS Installation - 

1) sudo apt install nodejs npm -y
2) node -v

- NodeJS Mise à jour - 

1) sudo npm cache clean -f (facultatif, mais recommandé) 
2) sudo npm install -g n
3) sudo n stable

- Yarn installation - 

1) npm install --global yarn

---------------------------------------------------------------------------------------------------------------------------------------------------------

# Raspberry PI 4 (TEST perso. bidouillage)

- Modifier docker-compose-install (remplacer $(uname -m) par "armlv7l")
- Installation du moteur docker manuellement :
    1) sudo apt-get update
    2) sudo apt-get install \ ca-certificates \ curl \ gnupg \ lsb-release
    3) sudo mkdir -p /etc/apt/keyrings
    4) curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    5) echo \ "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \ $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    6) sudo apt-get update
    7) sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
    8) docker-compose build
    9) docker-compose up -d
    10) docker ps (vérification si les containers sont bien lancé)
