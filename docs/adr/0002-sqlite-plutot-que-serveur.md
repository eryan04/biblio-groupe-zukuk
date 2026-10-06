# ADR 0002 : SQLite plutôt qu'un fichier JSON ou un serveur PostgreSQL

- Statut : accepté
- Date : 2026-10-05
- Décideurs : équipe Zukuk

## Contexte

Biblio est une petite application en ligne de commande destinée à gérer la collection d'une association. Elle doit fonctionner localement, être simple à installer et permettre de conserver les livres, les adhérents et l'historique des prêts.

Les données sont relationnelles : un prêt relie un livre à un adhérent, et les commandes doivent pouvoir retrouver les prêts actifs ou en retard. Le projet doit donc enregistrer les données de façon cohérente tout en gardant une installation légère, sans service à administrer.

## Options envisagées

1. **Un fichier JSON** : stockage direct dans un fichier texte, sans moteur de base de données.
2. **SQLite** : base relationnelle intégrée, stockée dans un fichier local.
3. **PostgreSQL** : base relationnelle serveur, à installer et à administrer séparément de l'application.

## Décision

Nous retenons SQLite. La bibliothèque `sqlite3` est incluse avec Python, et la base peut être conservée dans un seul fichier local. SQLite fournit le langage SQL, les requêtes relationnelles, les transactions et les contraintes de clés étrangères utiles aux livres, adhérents et prêts, sans imposer de serveur.

## Conséquences

- L'installation et l'exécution restent simples : aucun serveur de base de données ni dépendance Python externe n'est nécessaire.
- Les données sont structurées et interrogées avec SQL plutôt qu'avec du code spécifique à la lecture, à la modification et à la réécriture d'un fichier JSON.
- Les transactions aident à éviter les mises à jour partielles, et les contraintes relationnelles permettent de protéger les liens entre prêts, livres et adhérents.
- La base reste locale au fichier : l'équipe doit veiller à sauvegarder ce fichier et à éviter les modifications concurrentes importantes. SQLite convient au volume et à l'usage actuels, mais offre moins de possibilités de connexions simultanées qu'un serveur de base de données.
- PostgreSQL demanderait l'installation, la configuration, l'administration et une connexion au serveur. Ces coûts ne sont pas justifiés pour l'application actuelle. Si Biblio devient un service partagé par plusieurs postes ou nécessite des accès concurrents soutenus, nous réévaluerons cette décision et pourrons migrer vers PostgreSQL.
- JSON serait envisageable pour des données très simples ou un export, mais il faudrait réimplémenter la gestion des relations, de la cohérence des mises à jour et des requêtes, ce qui est inadapté aux prêts et adhérents de Biblio.