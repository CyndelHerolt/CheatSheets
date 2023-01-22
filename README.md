---
description: Une alternative aux VM
---

# L'écosystème Docker

## Docker Engine

<mark style="color:yellow;">**Docker Server**</mark> est le processus **Docker Daemon**, un programme qui fonctionne en arrière-plan et qui <mark style="color:blue;">attend de recevoir des instructions à transmettre au reste des composantes de Docker</mark>. Son accès est très limité et est régi par une API.\
Afin d'intéragir avec cette API, on utilise **Docker CLI** (Command Line Interface) qui offre un accès à des lignes de commandes spécifiques. C'est ce qu'on appelle <mark style="color:yellow;">**Docker Client**</mark>.

L'ensemble des deux forme le <mark style="color:yellow;">**Docker Engine.**</mark>

## Docker File

Le <mark style="color:yellow;">**Docker File**</mark>, c'est un fichier dans lequel on va <mark style="color:blue;">lister tout ce dont on a besoin pour faire fonctionner une application</mark> (ex. Ubuntu, Nginx, Angular, Node).

A partir du **Docker File**, on va pouvoir exploiter **Docker CLI**. On va lui demander de transmettre à **Docker Daemon** notre volonté de créer une Image. \
<mark style="color:blue;">Cette Image sera finalement l'ensemble des dépendances que l'on a listées dans le Docker File</mark>, construites par **Docker Daemon**. Elle contient la quantité de code minimale permettant de faire fonctionner de manière autonome (sous Linux) les dépendances qui la compose.

## Docker Image

Lorsque l'on sollicite **Docker Daemon** pour la création d'une Image, il va chercher le code dont il a besoin dans ce qu'on appelle le <mark style="color:yellow;">**Docker Registry**</mark>. De la même manière que GitHub propose des bibliothèque de code, <mark style="color:yellow;">**DockerHub**</mark> propose une bibliothèque de dépendances (qui sont elles-mêmes des **Docker Image**) qui seront téléchargées sur votre disque dur lors de la création de votre **Image**. Ce qui signifie qu'une <mark style="color:blue;">Docker Image est en fait un ensemble de Docker Image assemblées afin de former un fragment d'environnement qui viendra complémenter l'environnement de la machine.</mark>

Une fois installées sur votre disque dur, les **Images** ne sont accessibles qu'en lecture seule. Elles sont donc <mark style="color:blue;">toujours exactement similaires</mark>, peu importe le nombre d'images supplémentaires qui sont construites en les incluants. On ne stocke alors une image qu'une seule fois et elle est <mark style="color:blue;">lue par ses images parentes lorsque c'est nécessaire</mark>.

## Volume

Si l'**Image** n'est accessible qu'en lecture seule, il paraît compliqué de stocker des informations persistantes dans le serveur web si il est construit avec des **Docker Image** (ex. données de database). On utilise alors des <mark style="color:yellow;">**Volumes**</mark>.\
Un **Volume** est un espace sur votre disque dur sur lequel l'image va pouvoir <mark style="color:blue;">écrire et stocker des informations persistantes afin de les récupérer plus tard</mark>. C'est à partir de cet ensemble Docker Image et Volume (+ conf. si on veut par exemple rediriger des ports) que l'on va pouvoir créer un <mark style="color:yellow;">**Docker Container**</mark>.

## Docker Container

Un **Docker Container** **est un processus**, là ou une **Docker Image** **est un programme**. Dans ce sens, <mark style="color:blue;">**Docker Image**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">est une certaine quantité de code, ici l'ensemble des dépendances nécessaires à la création de l'Image et</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Docker Container**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">est simplement l'éxecution de ce code, de cette Image.</mark> On peut donc, à partir d'une seule **Docker Image**, lancer plusieurs **Docker Container**.

On va également pouvoir exploiter des <mark style="color:blue;">groupements de</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Container**</mark>. On peut par exemple, pour une même application, avoir un **Container** dédié à la distribution de l'application web, un **Container** dédié à la gestion de la database et un autre **Container** dédié à l'éxecution de calcul etc. \
Ces groupements sont appelés des <mark style="color:yellow;">**Node**</mark>. <mark style="color:blue;">Dans ces</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Node**</mark><mark style="color:blue;">, les</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Container**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">vont être en mesure d'intéragir les uns avec les autres</mark>. On pourra également les dupliquer et c'est alors qu'un <mark style="color:yellow;">**Manager**</mark> s'occupera de répartir la charge de travail entre les différents **Node**, pour éviter de l'une d'entre elles soit trop sollicitée.\
Pour définir la configuration des **Node**, on va utiliser <mark style="color:yellow;">**Docker Compose**</mark> qui va se charger d'organiser le travail des différents **Container** qui les composent.&#x20;

<mark style="color:blue;">L'ensemble de plusieurs</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Node**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">et leur</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Manager**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">constitue un</mark> <mark style="color:yellow;">**Cluster**</mark><mark style="color:blue;">.</mark>
