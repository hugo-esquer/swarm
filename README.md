# Docker Swarm
## Checklist
### Préparation des machines
- Créer les VMs Débian (1 manager, 2 workers, 1 NFS)
- Installer Docker sur toutes la machines
- configurer SSH entre les noeuds pour faciliter le bootstrap
### Configuration du cluster
- Initialiser le cluster Swarm (docker swarm init)
- Joindre les workers au cluster (docker swarm join)
- Configurer le NFS et monter les volumes sur chaque noeud
### Déploiement des services
- Déployer un Docker registry privé
- Déployer une stack Docker Swarm (via Docker stack deploy) avec :
  - MariaDB (avec volume persistant)
  - PHP
  - Nginx configuré en proxy
  - VSCode Server
- Configurer les réseaux Docker et les volumes partagés
### Sécurité et résilience
- Sécuriser le registry (auth + HTTPS)
- Chiffrer les communications Swarm (activé par défault)
- Option : Activer la surveillance (Prométheus + Graphana)
