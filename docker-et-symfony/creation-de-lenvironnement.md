# Création de l'environnement

## Via les outils proposés par Symfony

Si vous souhaitez utiliser Docker avec Symfony de manière simple et rapide, vous pouvez utiliser le projet Symfony Docker officiellement proposé par Symfony. Ce projet fournit une configuration Docker prête à l'emploi pour démarrer rapidement avec Symfony et Docker.

{% hint style="warning" %}
Cette méthode, telle quelle, ne fonctionne que sur une config en local. Si vous voulez tester ça sur, par exemple une VM Multipass, il faudra suivre adapter votre config de cette manière.
{% endhint %}

Voici comment vous pouvez obtenir et utiliser le projet Symfony Docker :

1. **Cloner le projet Symfony Docker** :
   * Vous pouvez cloner le projet Symfony Docker à partir de son dépôt GitHub en utilisant la commande suivante:

```sh
git clone https://github.com/dunglas/symfony-docker.git
```

Dans le dossier du projet cloné, lancer les commandes :&#x20;

```sh
docker compose build --no-cache
# construit et lance un nouveau projet symfony
docker compose up --pull always -d --wait
```

{% hint style="warning" %}
Ce processus prend un certain temps à s'executer entièrement, profitez-en pour lire la doc&#x20;
{% endhint %}

Ensuite vous pouvez accéder à votre projet via [https://localhost](https://localhost)&#x20;

{% hint style="info" %}
Si vous faites face à un avertissement de sécurité dans votre navigateur, vous pouvez modifier les paramètres afin d'[`accepter les certificats TLS auto-générés`](https://stackoverflow.com/questions/7580508/getting-chrome-to-accept-self-signed-localhost-certificate/15076602#15076602)
{% endhint %}

Pour arrêter les containers Docker il vous suffit de faire :&#x20;

```bash
docker compose down --remove-orphans
```

## Via la méthode manuelle

Pour faire fonctionner un projet Symfony dans un environnement Docker, il vous faut d'abord initialiser le projet Symfony. (cf. [Symfony](https://app.gitbook.com/s/f7vqQ2Kol4hyX8Z5JDQh/modes-operatoires/creation-dune-application))

Dans ce projet Symfony, il faut créer un fichier docker-compose.yml qui contiendra la configuration.
