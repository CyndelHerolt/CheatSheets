---
description: >-
  Docker nécessite un environnement Linux pour fonctionner. Son installation,
  quelle soit sous Windows ou OS implique forcément l'installation d'un
  Sous-système Linux (WSL2, lima-vm ...).
---

# Installation

## Installation sous Linux, Ubuntu ou Debian

{% embed url="https://docs.docker.com/desktop/install/linux-install/" %}

{% embed url="https://docs.docker.com/desktop/install/ubuntu/" %}

{% embed url="https://docs.docker.com/desktop/install/debian/" %}

## Installation sous Windows et MacOS

Pour pouvoir utiliser Docker dans un environnement Windows, il est nécessaire de passer par une VM fonctionnant sous Linux. Une fois **Docker Desktop** installé, il faudra obligatoirement le lancer avant d'utiliser Docker ; car son lancement initiera Docker dans la VM.

{% embed url="https://docs.docker.com/desktop/install/windows-install/" %}

Il faut utiliser le <mark style="color:yellow;">**terminal Bash**</mark> afin d'avoir accès à toutes les commandes. Pour y parvenir, on doit installer Git. Une fois l'installation de Git effectuée, il suffit d'ouvrir <mark style="color:yellow;">**Git Bash**</mark> afin d'accéder au command prompt.

{% embed url="https://git-scm.com/book/en/v2/Getting-Started-Installing-Git" %}

L'installation de **Docker Desktop** sous MacOS entraîne automatiquement l'installation d'un terminal utilisable pour la saisie des commandes de **Docker client**.

{% embed url="https://docs.docker.com/desktop/install/mac-install/" %}

