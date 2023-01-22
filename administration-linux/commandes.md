---
description: Liste de commandes Linux
---

# Commandes

## Déplacements dans l'arborescence, manipulation de fichiers et dossiers

| Commande                                                            | Description                                                                           |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `ls`                                                                | Liste tous les fichiers du répertoire courant                                         |
| `ls -R`                                                             | Liste en plus les fichiers du sous-répertoire                                         |
| `ls -a`                                                             | Liste en plus les fichiers cachés                                                     |
| `ls -al`                                                            | Liste les fichiers, dossiers et leurs détails (permissions, taille, propriétaire ...) |
| `cd or cd ~`                                                        | Se déplacer au répertoire HOME                                                        |
| `cd ..`                                                             | Se déplacer un niveau au-dessus                                                       |
| `cd`                                                                | Se déplacer vers un dossier en particulier                                            |
| `cd /`                                                              | Se déplacer à la racine                                                               |
| `cat > filename`                                                    | Créer un nouveau fichier                                                              |
| `cat filename`                                                      | Afficher le contenu du fichier                                                        |
| `cat file1 file2 > file3`                                           | Combiner deux fichiers pour en créer un nouveau                                       |
| `nano filename`                                                     | Créer un nouveau fichier                                                              |
| `touch`                                                             | Créer un fichier vide                                                                 |
| `mv`                                                                | Déplacer ou renommer un fichier \| dossier                                            |
| `rm`                                                                | Supprimer un fichier \| dossier                                                       |
| `cp`                                                                | Copier un fichier \| dossier                                                          |
| `pwd`                                                               | Afficher le répertoire courant                                                        |
| Pour spécifier qu'on a un dossier et pas un fichier un utilise `-R` | Exemple : `rm -R nomDuDossier`                                                        |
| <p><code>apt install</code><br><code>apt update</code></p>          | Installer \| Mettre à jour les paquets                                                |
| `sudo`                                                              | Devenir superUser                                                                     |
| `man`                                                               | Obtenir de l'aide pour une commande                                                   |
| `history`                                                           | Obtenir une liste de toutes les commandes saisies dans la session                     |
| `clear`                                                             | Vider le terminal                                                                     |

## Gestion des utilisateurs, des groupes et de leurs droits

| Commande                                                                                               | Description                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `adduser NomUser Mdp`                                                                                  | Créer un utilisateur                                                                                                                                   |
| `userdel NomUser Mdp`                                                                                  | Supprimer un utilisateur                                                                                                                               |
| `groupadd NomGroupe`                                                                                   | Créer un groupe                                                                                                                                        |
| `groupdel NomGroupe`                                                                                   | Supprimer un groupe                                                                                                                                    |
| `groupmod NomGroupe`                                                                                   | Modifier un groupe                                                                                                                                     |
| `groups NomUser`                                                                                       | Voir à quel groupe appartient un utilisateur                                                                                                           |
| `usermod -aG NomGroupe NomUser`                                                                        | Ajouter un utilisateur dans un groupe                                                                                                                  |
| <p><code>chown NomUser:NomGroupe fichier</code><br><code>chown -R NomUser:NomGroupe dossier</code></p> | Changer le propriétaire d'un fichier \| dossier                                                                                                        |
| `chmod xxx NomFichier`                                                                                 | Modifier les droits d'un fichier \| dossier                                                                                                            |
| <mark style="background-color:orange;">**permissions**</mark>                                          | <mark style="background-color:orange;">**Notation décimale**</mark>                                                                                    |
| `r` (lecture)                                                                                          | 4                                                                                                                                                      |
| `w` (écriture)                                                                                         | 2                                                                                                                                                      |
| `x` (exécution)                                                                                        | 1                                                                                                                                                      |
| On additionne les valeurs pour appliquer les permissions.                                              | <p>La première valeur est pour l'utilisateur qui saisi la commande. <br>La deuxième pour son groupe.<br>La troisième pour les autres utilisateurs.</p> |

## Gestion Réseau

| Commande                                                                | Description                                                            |
| ----------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `ssh username@ip-address or hostname`                                   | Se connecter sur une machine à distance en ssh                         |
| `ping adresseIP`                                                        | Analyser le réseau et les connexions                                   |
| `ifconfig`                                                              | Configurer et afficher les infos des interfaces réseaux                |
| <p><code>ifconfig eth0 up</code><br><code>ifconfig eth0 down</code></p> | Modifier le statut d’une interface réseau d’inactif à actif (ici eth0) |
| `ifconfig eth0 adresseIP`                                               | Attribuer une adresse IP à une interface                               |
| `ifconfig eth0 netmask adresseIP`                                       | Définir un masque de réseau pour une interface                         |
| `ss`                                                                    | Afficher des infos sur les connexions réseaux.                         |
| `ss -tunlp`                                                             | Afficher les ports TCP et UDP utilisés                                 |
|                                                                         |                                                                        |
