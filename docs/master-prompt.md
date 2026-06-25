# Master Prompt — Installation des commandes

Copie-colle le bloc ci-dessous en une seule fois dans Claude Code pour créer les 5 commandes automatiquement.

---

```
Crée les 5 commandes Claude Code suivantes. Pour chaque commande, crée le fichier correspondant dans .claude/commands/.

---

/spec
Tu m'interviewes une question à la fois pour comprendre mon projet. Tu ne passes pas à la suivante tant que ma réponse n'est pas claire. Une fois que tu as tout, tu écris specs/projet.md avec exactement ces sections :
- Objectif (1 phrase)
- Contexte tech (stack, langage, framework, environnement, CI/CD)
- Besoins fonctionnels (liste numérotée, chaque item est vérifiable)
- Besoins non-fonctionnels (tests, performance, sécurité, conventions)
- Cas limites (ce qui ne doit pas arriver)
- Définition de terminé (critères objectifs, pas d'interprétation)
Tu ne construis rien. Tu confirmes le fichier écrit à la fin.

---

/adapt
Tu lis la section "Contexte tech" dans specs/projet.md. Tu adaptes ton comportement pour le reste de la session : conventions de nommage, structure de fichiers, format des tests, style de code, outils de build. Tu affiches une confirmation de ce que tu as détecté et comment tu vas t'adapter. Cette commande ne modifie pas le code.

---

/build
Tu lis specs/projet.md et specs/progress.md si il existe. Tu construis exactement ce qui est décrit dans les besoins fonctionnels, dans l'ordre, en respectant le contexte tech. Tu ne construis rien qui ne soit pas dans le spec. Après chaque besoin couvert, tu mets à jour specs/progress.md avec : ce qui est fait, ce qui reste, les décisions techniques prises. À la fin tu affiches un résumé de ce que tu as couvert.

---

/review
Tu lis specs/projet.md et tout le code produit. Tu compares point par point chaque besoin fonctionnel et non-fonctionnel. Tu classes les écarts en 3 catégories :
- MANQUANT : besoin non implémenté
- BUGUÉ : implémenté mais incorrect
- HORS-SPEC : code produit qui n'est pas dans le plan
Pour MANQUANT et BUGUÉ tu écris les corrections et tu relances /build automatiquement. Pour HORS-SPEC tu me demandes si je veux garder ou supprimer. Si tu as déjà renvoyé vers /build 3 fois sur le même point sans succès, tu t'arrêtes et tu m'expliques le blocage. Tu ne valides que quand tous les besoins fonctionnels et non-fonctionnels sont couverts.

---

/checkpoint
Tu lis specs/projet.md et specs/progress.md. Tu écris un résumé clair dans specs/progress.md : pourcentage estimé de complétion, besoins couverts, besoins restants, blocages identifiés, décisions prises. Tu affiches ce résumé dans le chat. Cette commande ne modifie pas le code.
```
