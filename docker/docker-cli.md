---
description: Quelques commandes utiles pour l'utilisation de Docker CLI
---

# Docker CLI

<mark style="color:yellow;">**Docker CLI**</mark>** ** ou <mark style="color:yellow;">**Docker Client**</mark>** ** permet d'intéragir avec Docker par l'intermédiaire du command prompt.\
Voici une liste non exhaustive des commandes disponibles :

| Commande                      | Description                                                                                                             |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| docker                        | Affiche une liste de commandes disponibles dans le Docker CLI.                                                          |
| docker info                   | Affiche des informations sur **Docker Client** (CLI) et **Docker Server** (Daemon). ex. nbr de Container, version OS... |
| docker image ls               | Liste toutes les images présentes localement sur notre machine                                                          |
| docker image -f rm NOM\|\|ID  | Supprime une image \| ajouter `-f` si l'image est utilisé dans un container                                             |
| docker container ls -a        | Liste tous les container actifs \| ajouter `-a` pour voir les container non actifs                                      |
| docker container rm NOM\|\|ID | Supprime un container                                                                                                   |
| docker container prune        | Supprime tous les container non actifs                                                                                  |
