# Mon Lab 2 sur Vagrant
Ce lab consiste à créer deux machines virtuelles en utilisant Vagrant, un outil permettant de créer des environnements virtuels de manière automatisée. Vagrant fait partie des outils d'Infrastructure as Code (IaC), tout comme Terraform. et utilise ssh pour se connecter au server sans mot de passe en utilisant un cle ssh.

## Les etapes pour lancer ce projet 

1. Clonez le dépôt : ```git clone https://github.com/Oumar3/vagrantlab2.git```

2. Se deplacer dans le dossier qui se trouve vagrantfile : ```cd vagrantlab2```
3. lancer la creation des vm avec la commande : ```vagrant up --provision```

### Verifier pour que les deux vm marchent normalemet
1. Verifier  le server docker est bien installer : ```vagrant ssh docker-server```
2. Verifier le server ngnix est bien installer : ```vagrant ssh ngnix-server``` 

## Connexion avec ssh en utilisant ssh-key

1. create un key ssh sur ton client avec la commande : ``ssh-keygen -t rsa -b 4096``
2. se deplacer dans le dossier : ``cd .ssh``
3. verifie que le ssh key bien generer: `` ls dans le repertoir .ssh ``
2. copy le key public sur ton server distant avec la commande : `` ssh-copy-id user@Ip-address de server distant`` 


## se connecter sur le server

``` ssh user@Ip-address de server distant```