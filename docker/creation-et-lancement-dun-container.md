# Création et lancement d'un Container

Après avoir lancé Docker Desktop, ouvrez un terminal Git Bash.

## 1. En théorie

### <mark style="color:yellow;">1.Création d'un Container à partir d'une Image</mark>

Saisir la commande suivante permet de créer un Container à partir d'une Image :&#x20;

```bash
docker run nomDeLimage
```

Cette commande engendre le comportement suivant :&#x20;

1. Le <mark style="color:blue;">**Docker CLI**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">envoie une requête à Docker Daemon</mark>, qui est de créer un Container à partir de l'Image demandée.
2. Le premier réflexe de **Docker Daemon** est de vérifier si l'Image en question est disponible sur la machine. Si ce n'est pas le cas, il va aller la chercher directement sur **Docker Hub** afin de <mark style="color:blue;">la télécharger</mark>.
3. **Docker Daemon** <mark style="color:blue;">créé un nouveau Container à partir de cette Image</mark> et éxecute immédiatement la ou les commande.s configurée.s pour être lancée.s à ce moment là.
4. **Docker Daemon** <mark style="color:blue;">renvoie des informations à Docker Client</mark> qui peuvent par exemple nous être retournées dans le terminal.

{% hint style="info" %}
Le Container étant complètement isolé du terminal, l'information qui nous est retournée est en fait récupérée par Docker Daemon dans le Container et qui la communique au Docker Client.
{% endhint %}

Si on retape exactement la même commande pour executer la même Image, <mark style="color:blue;">Docker Daemon recréé un Container à partir de l'Image</mark>. Mais cette dernière est déjà présente localement grace à la commande précédente, elle est donc <mark style="color:blue;">accessible directement dans votre machine car stockée par Docker Daemon</mark>.

### <mark style="color:yellow;">1.2 Lancement d'un Container</mark>

Lorsque l'on créé un Container à partir d'une Image, celui-ci s'interrompt automatiquement une fois qu'il a executé ce pourquoi il a été programmé.&#x20;

Si on veut que le Container continue de tourner après avoir téléchargé et installé l'image, il faut taper la commande `docker run` avec quelques instructions supplémentaires :&#x20;

```bash
docker run -it nomDeLimage
```

* L'option <mark style="color:yellow;">`-i`</mark> permet de <mark style="color:blue;">lancer un Container en mode Interactif</mark>. Cela signifie que l'on pourra intéragir avec le Container en question à partir du terminal dans lequel on est.
* L'option <mark style="color:yellow;">`-t`</mark> permet de <mark style="color:blue;">lancer le shell par défaut de l'image</mark> et donc de proposer l'affichage d'un prompt qui facilite la navigation dans le Container.

### <mark style="color:yellow;">1.3 Spécificité d'un Docker Container</mark>

Après avoir lancé le Container en mode Interactif en lui spécifiant de lancer son propre shell, on se retrouve dans son arborescence. Il doit normalement y avoir les fichiers nécessaires au fonctionnement de l'Image à partir de laquelle il a été créé. \
C'est sensiblement similaire à ce qu'on retrouve dans une VM à quelques exceptions près.&#x20;

Pour commencer, il ne faut pas oublier qu'un Container est complètement isolé du système d'exploration de fichiers de la machine hôte. Il est donc impossible d'accéder à des données présentes localement à partir du Container et inversement de la machine au Container.  &#x20;



## 2. En pratique

#### Créer un Container à partir de l'Image de la distribution Linux ultra-légère : Alpine

Saisir la commande suivante pour un Container à partir de l'Image Alpine :&#x20;

```bash
docker run alpine
```
