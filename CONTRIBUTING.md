# Contribuer à Biblio

Ce guide explique comment proposer une modification au projet et la faire relire. Il s'adresse aux membres actuels et aux nouvelles personnes qui rejoignent l'équipe.

## Avant de commencer

- Consultez le [README](README.md) pour installer et lancer Biblio.
- Vérifiez les [issues ouvertes](../../issues) pour voir si le problème ou l'idée a déjà été signalé.
- Pour signaler un bug, utilisez le modèle « Signaler un bug ». Pour proposer une évolution, utilisez « Proposer une évolution ». Si vous ne savez pas si le comportement est normal, utilisez « Poser une question ».
- Décrivez les étapes précises pour reproduire un bug, le résultat attendu et le résultat observé. Ne partagez pas de données personnelles d'adhérents.

## Créer une branche

Les changements se font dans une branche créée à partir de `main` à jour. Ne poussez jamais directement sur `main` : toute modification passe par une pull request relue.

Utilisez un nom descriptif qui indique le sujet, par exemple :

- `fix/12-refuse-double-pret` pour un correctif lié à l'issue 12 ;
- `feature/3-afficher-emprunteur` pour une évolution ;
- `docs/15-contributing` pour de la documentation.

Gardez chaque branche et chaque pull request centrées sur un seul sujet.

## Modifier et tester

- Suivez les conventions et la structure déjà présentes dans le dépôt.
- Ajoutez ou adaptez des tests quand le comportement change.
- Lancez les tests depuis la racine du dépôt avant d'ouvrir la pull request :

  **Windows (Command Prompt)**
  ```bat
  py -m unittest discover -s tests -t . -v
  ```

  **Linux / WSL**
  ```bash
  python3 -m unittest discover -s tests -t . -v
  ```

- Vérifiez `git status` et ne soumettez que les fichiers liés à votre changement.

## Commit et pull request

1. Faites des commits avec un message court qui décrit l'action, par exemple `fix: reject loans for unknown members` ou `docs: explain contribution workflow`.
2. Poussez votre branche sur GitHub.
3. Ouvrez une pull request vers `main`. Utilisez le modèle du dépôt et renseignez les sections **Contexte**, **Changements**, **Impact** et **Comment tester**.
4. Reliez l'issue concernée avec `Closes #<numéro>` dans la description.
5. Sélectionnez au moins un camarade comme reviewer et attendez sa review. Répondez aux commentaires et corrigez les changements demandés sur la même branche.
6. Après approbation et vérification des tests, l'équipe peut merger la pull request. Supprimez ensuite la branche si GitHub ne le fait pas automatiquement.

Ne mergez pas une pull request qui n'a pas été relue ou dont les tests échouent.
