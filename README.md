# Biblio
Ce projet est une application permettant de gérer facilement une collection de livres, conçue pour les bibliothécaires et les passionnés de lecture.

## Prérequis
- Python 3 installé.

## Installation
Ouvrez un terminal à la racine du projet, dans le dossier qui contient `biblio.py`.

- **Windows** : dans l’explorateur de fichiers, ouvrez le dossier du projet, puis utilisez `Repository > Open in Command Prompt` pour ouvrir l’Invite de commandes dans ce dossier.
- **WSL** : ouvrez votre terminal WSL et placez-vous dans le dossier du projet avec `cd biblio-groupe-zukuk`.

## Utilisation

Les commandes ci-dessous sont à saisir dans le terminal indiqué au-dessus de chaque bloc. Ne saisissez pas les exemples de résultats : ils montrent seulement ce que le programme affiche.

### 1. Créer la base de données

À faire en premier. Cette commande crée le fichier `biblio.db` avec 6 livres et 3 membres pour tester. **Attention : si la base existe déjà, elle est effacée et recréée.**

**Windows — Invite de commandes (Command Prompt)** :

```bat
py biblio.py init
```

**WSL — terminal Linux (Bash)** :

```bash
python3 biblio.py init
```

Résultat attendu dans les deux systèmes :

```text
Base initialisee : 6 livres, 3 membres.
```

### 2. Voir tous les livres

Affiche la liste des livres et indique si chaque livre est disponible ou emprunté.

**Windows — Invite de commandes (Command Prompt)** :

```bat
py biblio.py livres
```

**WSL — terminal Linux (Bash)** :

```bash
python3 biblio.py livres
```

Exemple de résultat dans les deux systèmes :

```text
[1] L'Etranger (Albert Camus) : disponible
[2] Dune (Frank Herbert) : emprunte
[3] Le Petit Prince (Antoine de Saint-Exupery) : disponible
[4] Fondation (Isaac Asimov) : disponible
[5] Les Miserables (Victor Hugo) : disponible
[6] Neuromancien (William Gibson) : disponible
```

### 3. Chercher un livre

Saisissez un mot du titre. Le programme affiche les livres qui contiennent ce mot.

**Windows — Invite de commandes (Command Prompt)** :

```bat
py biblio.py chercher Petit
```

**WSL — terminal Linux (Bash)** :

```bash
python3 biblio.py chercher Petit
```

Exemple de résultat dans les deux systèmes :

```text
[3] Le Petit Prince (Antoine de Saint-Exupery)
```

### 4. Emprunter un livre

Saisissez d’abord le numéro du livre, puis celui du membre. Exemple : le membre 1 emprunte le livre 3.

**Windows — Invite de commandes (Command Prompt)** :

```bat
py biblio.py emprunter 3 1
```

**WSL — terminal Linux (Bash)** :

```bash
python3 biblio.py emprunter 3 1
```

Exemple de résultat dans les deux systèmes :

```text
Emprunt enregistre : livre 3, membre 1.
```

Si le membre n’existe pas, le programme affiche une erreur. Exemple de commande :

**Windows — Invite de commandes (Command Prompt)** :

```bat
py biblio.py emprunter 2 9
```

**WSL — terminal Linux (Bash)** :

```bash
python3 biblio.py emprunter 2 9
```

Résultat dans les deux systèmes :

```text
Erreur : membre 9 introuvable.
```

### 5. Rendre un livre

Saisissez le numéro du livre rendu.

**Windows — Invite de commandes (Command Prompt)** :

```bat
py biblio.py rendre 3
```

**WSL — terminal Linux (Bash)** :

```bash
python3 biblio.py rendre 3
```

Exemple de résultat dans les deux systèmes :

```text
Retour enregistre pour le livre 3.
```

### 6. Voir les retards

Un livre est en retard si on le garde plus de 14 jours. Le nombre de jours dépend de la date à laquelle la commande est exécutée.

**Windows — Invite de commandes (Command Prompt)** :

```bat
py biblio.py retards
```

**WSL — terminal Linux (Bash)** :

```bash
python3 biblio.py retards
```

## Tests

Lancez les tests depuis la racine du projet.

**Windows — Invite de commandes (Command Prompt)** :

```bat
py -m unittest discover -s tests -t . -v
```

**WSL — terminal Linux (Bash)** :

```bash
python3 -m unittest discover -s tests -t . -v
```

## Structure du projet

```text
biblio-groupe-zukuk/
├── .github/
│   ├── ISSUE_TEMPLATE/       # Modèles d’issues GitHub
│   ├── workflows/
│   │   └── tests.yml         # Exécution automatique des tests
│   └── pull_request_template.md
├── docs/
│   ├── adr/                  # Décisions d’architecture
│   └── circulation.md        # Documentation sur la circulation des livres
├── exercices/                # Exercices du projet
├── tests/
│   └── test_biblio.py        # Tests automatisés
├── biblio.py                 # Application et commandes
├── README.md                 # Guide du projet
└── .gitignore
```

Le fichier `biblio.db` est créé à la racine lorsque vous initialisez la base. Il est ignoré par Git et n’apparaît donc pas dans la structure suivie par le dépôt.

## Contribuer
## Auteurs
RYAN ELQALI
KEREM
EDVIGE
