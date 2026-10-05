# Biblio
Ce projet est une application permettant de gérer facilement une collection de livres, conçue pour les bibliothécaires et les passionnés de lecture.

## Prérequis
## Installation

## Utilisation

On utilise le programme avec des commandes dans le terminal.
Il faut ouvrir le terminal dans le dossier du projet (Repository > Open in Command Prompt).
Pour chaque commande : d'abord la commande à taper, puis le résultat affiché.

### 1. Créer la base de données

À faire en premier. Cette commande crée le fichier `biblio.db` avec 6 livres et 3 membres pour tester.
Attention : si la base existe déjà, elle est effacée et recréée.

```
python biblio.py init
```

```
Base initialisee : 6 livres, 3 membres.
```

### 2. Voir tous les livres

Affiche la liste des livres et dit si chaque livre est disponible ou emprunté.

```
python biblio.py livres
```

```
[1] L'Etranger (Albert Camus) : disponible
[2] Dune (Frank Herbert) : emprunte
[3] Le Petit Prince (Antoine de Saint-Exupery) : disponible
[4] Fondation (Isaac Asimov) : disponible
[5] Les Miserables (Victor Hugo) : disponible
[6] Neuromancien (William Gibson) : disponible
```

### 3. Chercher un livre

On écrit un mot du titre. Le programme montre les livres qui contiennent ce mot.

```
python biblio.py chercher Petit
```

```
[3] Le Petit Prince (Antoine de Saint-Exupery)
```

### 4. Emprunter un livre

On donne d'abord le numéro du livre, puis le numéro du membre.
Exemple : le membre 1 emprunte le livre 3.

```
python biblio.py emprunter 3 1
```

```
Emprunt enregistre : livre 3, membre 1.
```

Si le membre n'existe pas, le programme affiche une erreur :

```
python biblio.py emprunter 2 9
```

```
Erreur : membre 9 introuvable.
```

### 5. Rendre un livre

On donne le numéro du livre rendu.

```
python biblio.py rendre 3
```

```
Retour enregistre pour le livre 3.
```

### 6. Voir les retards

Un livre est en retard si on le garde plus de 14 jours.
Le nombre de jours change selon la date du jour (ce résultat date du 5 octobre 2026).

```
python biblio.py retards
```

```
Dune, emprunte par Alice Martin : 254 jours de retard
Fondation, emprunte par Bilal Haddad : 259 jours de retard
```

## Tests
## Structure du projet
## Contribuer
## Auteurs