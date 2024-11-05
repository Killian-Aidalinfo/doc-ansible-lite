
# Ansible Lite (Beta)

**Ansible Lite** est un outil d'automatisation léger conçu pour simplifier la gestion des infrastructures sans la complexité de l'Ansible traditionnel. Ce projet est né du besoin d'un système de gestion pour une dizaine de serveurs, sans la nécessité de mettre en place un serveur Ansible centralisé, ce qui nécessite des ressources physiques et matérielles.

Cette version est actuellement en **bêta** et en cours de développement. Si vous rencontrez des problèmes ou des bugs, n'hésitez pas à ouvrir une issue sur GitHub : [https://github.com/aidalinfo/ansible-lite/issues](https://github.com/aidalinfo/ansible-lite/issues).

Pour le moment, le projet est uniquement disponible pour les bases Debian en x64.

Une version 32 bits sera bientôt publiée, avec un support pour d'autres distributions Linux.

## Objectifs du projet

**Ansible Lite** à pour but d'être une solution légère, idéale pour les petites infrastructures. Contrairement à d'autres outils qui nécessitent des serveurs agents ou des configurations complexes, **Ansible Lite** repose sur un système simple qui surveille les dépôts GitHub avec un **watcher** (cron) pour détecter les changements et exécuter les actions appropriées.

L'un de mes autres objectifs sera de créer une gestion via CLI, un peu comme CrowdSec avec CSCLI.

J'aimerais aussi inclure une gestion client-serveur. L'objectif n'est pas de créer un fork d'Ansible, mais d'avoir une visualisation de nos clients et de leurs dernières actions.

## Fonctionnement

La fonctionnalité de base d'**Ansible Lite** repose sur la surveillance des dépôts GitHub. Voici son fonctionnement :

- **Aucune instruction SSH directe** : Contrairement à la plupart des outils de gestion d'infrastructure, **Ansible Lite** se concentre uniquement sur la surveillance des changements dans les dépôts GitHub.

- Un **watcher** est configuré avec un **cron** pour surveiller régulièrement les dépôts.

- À chaque exécution du cron, le watcher vérifie si un nouveau commit a été effectué depuis la dernière exécution.

- Si un nouveau commit est détecté, le **script d'entrée** défini dans le dépôt est automatiquement exécuté pour appliquer les mises à jour ou changements nécessaires.

## Pourquoi Ansible Lite ?

- **Simplicité** : Pas besoin de serveur Ansible dédié. L'outil fonctionne directement avec GitHub pour surveiller les changements et automatiser les tâches.

- **Légèreté** : Conçu pour des environnements qui ne nécessitent pas une infrastructure lourde.

- **Décentralisation** : En utilisant GitHub, vous pouvez gérer vos configurations et mises à jour de manière simple et efficace.

- **Automatisation via les commits** : Dès qu'un commit est poussé vers un dépôt surveillé, le système peut automatiquement déclencher le script d'entrée pour appliquer les mises à jour.

## Bêta en Développement

Le projet **Ansible Lite** est en bêta et encore en développement actif. Nous encourageons les utilisateurs à tester l'outil et à fournir des retours via des issues en cas de bugs ou de problèmes rencontrés : [Ouvrir une issue](https://github.com/aidalinfo/ansible-lite/issues).
