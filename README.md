# docker adrien

Machine docker (mise à jour de https://github.com/cnadal/machine_docker) :
- Testé sous distribution de basant sur le noyau débian. 
- PHP 8.0.13 
- MYSQL
- PHPMYADMIN

Prêt à l'emploi pour des projets Symfony v6.0.x (En cours d'amélioration et correction des bugs) 


1) sudo apt install git
2) git clone le repository
3) chmod 755 ./get-docker.sh 
4) ./get-docker.sh
5) chmod 755 ./install-docker-compose
6) ./install-docker-compose (Si vous rencontrez un soucis ici faites un ticket) 
7) nano .env (configuration)
8) docker-compose build
9) docker-compose up -d

 SI Erreur "Docker daemon ........ driver not connecting" 

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
