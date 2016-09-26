# Snapcraft
## Installation
    sudo apt install snapcraft

## Commandes
    snapcraft --version // Retourne la version
    snapcraft tour // Création du snapcraft tour pour apprendre comment créer un paquet snap

## Création
Pour créer un paquet snap, il faut un fichier "snapcraft.yaml" (Ou ".snapcraft.yaml") qui décrira l'ensemble du processeur de construction du snap.
Pour lancer la procédure de création d'un snap, se placer là où est le fichier "snapcraft.yaml":
    snapcraft // Ou snapcraft snap
    snapcraft clean // Supprime les fichiers/dossiers nécéssaire lors du processus de création.
    snapcraft help // Aide
    install --force-dangerous <snapfile.snap> // Installe le snap qu'on vient de créer
