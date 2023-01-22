# Création d'un Container

Après avoir lancé Docker Desktop, ouvrez un terminal Git Bash.

## 1. Executer une Image

Saisir la commande suivante permet de créer un Container à partir d'une Image :&#x20;

```bash
docker run nomDeLimage
```

Cette commande engendre le comportement suivant :&#x20;

1. Le <mark style="color:blue;">**Docker CLI**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">envoie une requête à Docker Daemon</mark>, qui est de créer un Container à partir de l'Image demandée.
2. Le premier réflexe de Docker Daemon est de vérifier si l'Image en question est disponible sur la machine. Si ce n'est pas le cas, il va aller la chercher directement sur Docker Hub afin de <mark style="color:blue;">la télécharger</mark>.
3. Docker Daemon créé un nouveau Container à partir de cette Image et éxecute immédiatement la ou les commande.s configurée.s pour être lancée.s à ce moment là.
4.



&#x20;Si elle ne l'est pas, il va aller la chercher sur le Docker Hub afin de la télécharger.

