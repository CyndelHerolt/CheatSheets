# Initialisation de l'environnement

## Via les outils proposés par Symfony

Si vous souhaitez utiliser Docker avec Symfony de manière simple et rapide, vous pouvez utiliser le projet Symfony Docker officiellement proposé par Symfony. Ce projet fournit une configuration Docker prête à l'emploi pour démarrer rapidement avec Symfony et Docker.

{% hint style="warning" %}
Cette méthode, telle quelle, ne fonctionne que sur une config en local. Si vous voulez tester ça sur, par exemple une VM Multipass, il faudra suivre adapter votre config [de cette manière.](initialisation-de-lenvironnement.md#depuis-une-vm)
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

### Depuis une VM

Pour adapter la méthode officielle de Docker de Symfony à une configuration où vous utilisez une VM qui n'a pas pour IP localhost, vous devrez faire quelques ajustements dans la configuration Docker ainsi que dans les fichiers de configuration Symfony. Voici les étapes à suivre :

1. **Configurer Docker pour utiliser l'adresse IP de la VM Multipass** :
   * Dans le fichier `compose.yaml` (ou tout autre fichier Docker Compose utilisé), recherchez les occurrences de `localhost` et remplacez-les par l'adresse IP de votre VM Multipass. Vous devrez spécifier l'adresse IP de votre VM à la place de `localhost` dans les sections des services Docker comme `nginx` et `php`.
2. **Autoriser l'accès à votre application Symfony depuis l'extérieur** :
   * Assurez-vous que les règles de pare-feu sur votre VM Multipass autorisent l'accès aux ports utilisés par votre application Symfony. Vous devrez peut-être ouvrir les ports 80 (ou tout autre port que vous utilisez pour votre application) pour permettre à votre application Symfony d'être accessible depuis l'extérieur.
3. **Redémarrer les services Docker et tester votre application** :
   * Une fois que vous avez apporté ces ajustements, redémarrez vos services Docker en exécutant `docker-compose down` suivi de `docker-compose up -d`. Assurez-vous que vos conteneurs Docker se sont bien relancés sans erreur.
   * Testez ensuite votre application Symfony en accédant à l'adresse IP de votre VM Multipass depuis votre navigateur web.

En suivant ces étapes, vous devriez pouvoir adapter la méthode officielle de Docker de Symfony à votre configuration utilisant une VM Multipass. N'oubliez pas de sauvegarder vos fichiers de configuration avant d'apporter des modifications, au cas où vous auriez besoin de revenir en arrière.

## Via la méthode manuelle

Pour faire fonctionner un projet Symfony dans un environnement Docker, il vous faut d'abord initialiser le projet Symfony. (cf. [Symfony](https://app.gitbook.com/s/f7vqQ2Kol4hyX8Z5JDQh/modes-operatoires/creation-dune-application))

Dans ce projet Symfony, il faut créer un fichier docker-compose.yml qui contiendra la configuration.
