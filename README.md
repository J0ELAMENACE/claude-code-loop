# 🔁 Claude Code Loop System

Un système de 5 commandes pour Claude Code qui forme une loop de développement autonome, disciplinée et adaptable à n'importe quel type de projet.

```
/spec → /adapt → /build → /review → /build → ... → /checkpoint → ✅
```

## Pourquoi ?

Claude Code sur-génère par défaut. Ce système le contraint à :
- **Clarifier avant de construire** (`/spec`)
- **S'adapter à ta stack** (`/adapt`)
- **Construire strictement** (`/build`)
- **Vérifier et corriger** (`/review`)
- **Tracker l'état** (`/checkpoint`)

## Installation

### Option 1 — Copier les commandes directement

Clone le repo et copie le dossier `.claude/` à la racine de ton projet :

```bash
git clone https://github.com/TON_USERNAME/claude-code-loop.git
cp -r claude-code-loop/.claude/ ton-projet/
```

### Option 2 — Master prompt

Colle le contenu de [`docs/master-prompt.md`](docs/master-prompt.md) dans Claude Code. Il crée automatiquement toutes les commandes.

## Utilisation rapide

```
/spec       → interview + écriture du plan
/adapt      → calibration sur ta stack
/build      → construction stricte selon le spec
/review     → vérification et corrections
/checkpoint → snapshot en cas de pause ou blocage
```

## Les commandes

| Commande | Rôle | Modifie le code ? |
|---|---|---|
| `/spec` | Interview + plan dans `specs/projet.md` | ❌ |
| `/adapt` | Détecte la stack, calibre le comportement | ❌ |
| `/build` | Construit strictement selon le spec | ✅ |
| `/review` | Vérifie, catégorise les écarts, corrige | ✅ |
| `/checkpoint` | Snapshot de l'état dans `specs/progress.md` | ❌ |

## Structure générée dans ton projet

```
ton-projet/
├── .claude/
│   └── commands/
│       ├── spec.md
│       ├── adapt.md
│       ├── build.md
│       ├── review.md
│       └── checkpoint.md
├── specs/
│   ├── projet.md        ← source de vérité (généré par /spec)
│   └── progress.md      ← état courant (généré par /build et /checkpoint)
└── ... (ton code)
```

## Documentation

- [Guide d'utilisation complet](docs/guide.md)
- [Master prompt d'installation](docs/master-prompt.md)
- [Exemples par stack](docs/exemples-stack.md)

## Règles d'or

1. **Ne saute jamais `/spec`** — un brief vague = un résultat raté
2. **Lance `/adapt` après `/spec`** — surtout sur des stacks spécifiques
3. **`specs/projet.md` est sacré** — ne le modifie qu'entre deux cycles
4. **Si `/review` boucle 3 fois** — c'est un signal, pas un bug
5. **`/checkpoint` avant toute pause longue**

## Compatibilité

Testé et pensé pour : Go · Python · JavaScript/TypeScript · Rust  
CI/CD : GitLab CI · GitHub Actions  
Projets solo ou en équipe
