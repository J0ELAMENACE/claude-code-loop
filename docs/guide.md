# Guide d'utilisation — Claude Code Loop System

## Vue d'ensemble

Ce système repose sur 5 commandes qui forment une loop de développement autonome et disciplinée. Un seul fichier pilote tout : `specs/projet.md`.

```
/spec → /adapt → /build → /review → /build → ... → /checkpoint → ✅
```

---

## Démarrer un nouveau projet

### 1. `/spec` — Clarifier

Lance toujours par là. Claude t'interviewe question par question.

**Vérifie que le spec généré contient :**
- [ ] Objectif en 1 phrase
- [ ] Stack technique complète
- [ ] Besoins numérotés et vérifiables
- [ ] Contraintes non-fonctionnelles (tests, CI...)
- [ ] Définition claire de "terminé"

### 2. `/adapt` — Calibrer

Lance juste après `/spec`. Claude lit le contexte tech et ajuste ses conventions pour toute la session (nommage, structure, tests, style).

### 3. `/build` — Construire

Claude construit dans l'ordre du spec, rien de plus. Il met à jour `specs/progress.md` au fur et à mesure.

### 4. `/review` — Vérifier

Claude compare le code au spec point par point et catégorise les écarts :

| Catégorie | Action |
|---|---|
| **MANQUANT** | Relance `/build` automatiquement |
| **BUGUÉ** | Corrige et relance `/build` |
| **HORS-SPEC** | Te demande ton avis avant d'agir |

> ⚠️ Si `/review` renvoie 3 fois vers `/build` sur le même point sans succès, il s'arrête et t'explique le blocage. C'est voulu — ne force pas la loop.

### 5. `/checkpoint` — Snapshot

Génère un résumé complet dans `specs/progress.md`. Utile pour :
- Reprendre une session interrompue
- Débugger une loop qui tourne
- Faire un point avant de modifier le spec

---

## Reprendre un projet en cours

```
/checkpoint   ← voir où tu en étais
/adapt        ← re-calibrer la session
/build        ← continuer depuis progress.md
```

---

## Modifier le spec en cours de route

1. Lance `/checkpoint` pour sauvegarder l'état
2. Modifie `specs/projet.md` manuellement
3. Lance `/adapt` pour recalibrer
4. Lance `/build` — Claude reprend depuis `specs/progress.md`

> ⚠️ Ne modifie jamais le spec pendant un `/build` actif.

---

## Règles d'or

1. **Ne saute jamais `/spec`** — un brief vague = un résultat raté
2. **Lance toujours `/adapt` après `/spec`**
3. **`specs/projet.md` est sacré** — ne le modifie qu'entre deux cycles
4. **Fais confiance au blocage à 3 tentatives** — c'est un signal, pas un bug
5. **`/checkpoint` avant toute pause longue**
