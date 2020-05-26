# Post-installation setup script for CentOS 7 servers 

(c) Niki Kovacs, 2020


Ce repertoire fournit une un script de configuration  automatique post installation pour les serveurs fonctionnant sur CentOS7 ainsi qu'une collection de scripts d'aide et
modèles de fichiers de configuration pour les services communs

## En bref

Les etapes suivantes vont etre réalisées
  1. Installation minimal du system CentOS 7 

  2 Creation d'un utilisateur non root avec les privilèges administrateurs

  3. Installation de Git : 'sudo yum install git'

  4. Récupération du script

  5. Changement vers le nouveau répertoire : cd centos-7

  6. Lancement du script : 'sudo ./centos-setup.sh --setup`

  7. Attrapez une tasse de cafe pendant que le script fait tout son travail

  8. Redemarrage


## Personnalisation du serveur CentOS

Transformer une installation CentOS minimale en un serveur fonctionnel bout toujours
jusqu'à une série d'opérations plus ou moins longues. Votre kilométrage peut
varient bien sûr, mais voici ce que je fais habituellement sur une nouvelle installation CentOS :

  * Personnaliser le shell Bash : prompt, alias, etc.

  * Personnaliser l'éditeur Vim.

  * Installation des dépôts officiels et tiers.

  * Installer un ensemble complet d'outils en ligne de commande.

  * Supprimer une poignée de paquets inutiles.

  * Permettre à l'utilisateur administrateur d'accéder aux journaux du système.

  * Désactiver l'IPv6 et reconfigurer certains services en conséquence.

  * Configurer un mot de passe persistant pour `sudo`.

  * Etc.


Configurez Bash et Vim et définissez une résolution de console par défaut plus lisible 
```
# ./centos-setup.sh --shell
```

Mettre en place des dépôts officiels et des dépôts de tiers :
```
# ./centos-setup.sh --repos
```

Installez les groupes de paquets `Core` et `Base` avec quelques outils supplémentaires :

```
# ./centos-setup.sh --extra
```

Retirez une poignée de paquets inutiles :

```
# ./centos-setup.sh --prune
```

Permettre à l'utilisateur administrateur d'accéder aux journaux du système :

```
# ./centos-setup.sh --logs
```

Désactivez l'IPv6 et reconfigurez les services de base en conséquence :

```
# ./centos-setup.sh --ipv4
```

Configurez la persistance du mot de passe pour sudo :

```
# ./centos-setup.sh --sudo
```

Réalisez tout cela en une seule fois :

```
# ./centos-setup.sh --setup
```

Epurer les paquets et revenez à un système de base amélioré :

```
# ./centos-setup.sh --strip
```

Afficher un message d'aide

```
# ./centos-setup.sh --help
```

Si vous voulez savoir ce qui se passe exactement sous le capot, ouvrez un deuxième terminal
et de consulter les journaux :
```
$ tail -f /tmp/centos-setup.log
```

