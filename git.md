# GIT
## Installation
    sudo apt install git

## Configuration
    git config --global user.email "doctor-who@tardis"
    git config --global user.email "Doctor Who"

## Envoyer sur branche distante (Ici on pousse la branche master)
    git push origin master

## Recevoir depuis branche distante (Ici on reçoit de la branche master)
    git pull origin master

## Liste des dépôts distants
    git remote -v

## Liste des branches (Locales)
    git branch

## Créer une nouvelle branche (Et basculer immédiatement dessus)
    git checkout -b new_branch

## Fusionner une branche
    git checkout master (Se postionnne sur la branche master)
    git merge dev (Fusionne master avec dev, dans le sens dev vient dans master)

## Exemple : Ajout d'une branche distante (nom : origin) ssh (Avec un port inhabituel
   git remote add origin ssh://user@host:1234/srv/git/example

[Aide Github](https://help.github.com/categories/ssh/)
    
