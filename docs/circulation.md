# Circulation de l'information : groupe Zukuk

Document d'équipe à relire et mettre à jour collectivement lorsque les pratiques évoluent.

## 1. Rôles

- **Auteur d'une issue** : le membre qui observe le problème ou propose l'évolution la décrit et la reproduit avant de la publier avec le modèle adapté.
- **Auteur d'une pull request** : le membre qui réalise le changement sur sa branche, lance les vérifications et répond aux commentaires de review.
- **Reviewer** : un autre membre de l'équipe vérifie le changement, les tests et le lien avec l'issue, puis approuve ou demande des modifications.
- **Merge** : l'auteur de la pull request merge après approbation et réussite des vérifications requises. Personne ne pousse directement sur `main`.

## 2. Où circule chaque information

| Information | Qui la produit | Qui la valide | Où elle est stockée | Durée de vie |
|---|---|---|---|---|
| Code source | Auteur de la modification | Reviewer puis vérifications de la pull request | Dépôt GitHub, dans une branche puis sur `main` après merge | Tant que la fonctionnalité est maintenue |
| Bug signalé | Membre qui reproduit le problème | Équipe, par le triage et la review de la correction | Issue GitHub avec le modèle « Signaler un bug » | Jusqu'à résolution, puis conservé dans l'historique |
| Demande d'évolution | Membre qui décrit le besoin | Équipe, par discussion de l'issue et review de la pull request | Issue GitHub avec le modèle « Proposer une évolution » | Jusqu'à décision et réalisation éventuelle |
| Décision technique | Membre qui propose la décision | Équipe | ADR dans `docs/adr/` | Durable ; mise à jour si la décision est remplacée |
| Documentation d'installation | Membre qui modifie le guide | Reviewer de la pull request | `README.md` dans le dépôt | Tant qu'elle décrit la version courante |
| Question rapide entre membres | Tout membre | Personne concernée ou équipe | Discord | Éphémère ; reporter dans une issue ou la documentation si la réponse doit être conservée |
| Compte rendu et règles d'équipe | Équipe | Relecture collective | `docs/circulation.md` dans le dépôt | Durable ; révisé quand les règles changent |

## 3. Règles de l'équipe

- Avant de créer une issue, chercher si elle existe déjà et reproduire le comportement depuis une base initialisée lorsque c'est pertinent.
- Choisir le modèle correspondant : « Signaler un bug » pour un comportement incorrect, « Proposer une évolution » pour un besoin nouveau, « Poser une question » en cas de doute. Une question dont la réponse confirme un comportement normal est documentée puis fermée.
- Donner aux issues un titre précis décrivant ce qui se passe et où, plutôt que de recopier le message Discord.
- Les modèles appliquent les labels `bug`, `enhancement` ou `question`. Laisser l'assignation vide au moment du signalement ; l'équipe décide ensuite qui prend le sujet.
- Créer une branche depuis `main` à jour, avec un nom explicite et le numéro d'issue, par exemple `fix/12-refuse-double-pret` ou `docs/15-contributing`.
- Garder une seule intention par pull request. Renseigner le modèle de PR, inclure `Closes #<numéro>` quand une issue est résolue, indiquer les commandes de test et choisir un reviewer qui n'est pas l'auteur.
- Ne jamais pousser directement sur `main`. Toute modification est proposée par une pull request relue ; répondre aux commentaires et effectuer les corrections sur la même branche.
- Lancer les tests depuis la racine du dépôt avant la review : `python -m unittest discover -s tests -t . -v` (ou `py -m unittest discover -s tests -t . -v` sous Windows).
