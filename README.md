# ðŸ” Claude Code Loop System

Un systÃ¨me de 5 commandes pour Claude Code qui forme une loop de dÃ©veloppement autonome, disciplinÃ©e et adaptable Ã  n'importe quel type de projet.

```
/spec â†’ /adapt â†’ /build â†’ /review â†’ /build â†’ ... â†’ /checkpoint â†’ âœ…
```

## Pourquoi ?

Claude Code sur-gÃ©nÃ¨re par dÃ©faut. Ce systÃ¨me le contraint Ã  :
- **Clarifier avant de construire** (`/spec`)
- **S'adapter Ã  ta stack** (`/adapt`)
- **Construire strictement** (`/build`)
- **VÃ©rifier et corriger** (`/review`)
- **Tracker l'Ã©tat** (`/checkpoint`)

## Installation

### Option 1 â€” Copier les commandes directement

Clone le repo et copie le dossier `.claude/` Ã  la racine de ton projet :

```bash
git clone https://github.com/J0ELAMENACE/claude-code-loop.git
cp -r claude-code-loop/.claude/ ton-projet/
```

### Option 2 â€” Master prompt

Colle le contenu de [`docs/master-prompt.md`](docs/master-prompt.md) dans Claude Code. Il crÃ©e automatiquement toutes les commandes.

## Utilisation rapide

```
/spec       â†’ interview + Ã©criture du plan
/adapt      â†’ calibration sur ta stack
/build      â†’ construction stricte selon le spec
/review     â†’ vÃ©rification et corrections
/checkpoint â†’ snapshot en cas de pause ou blocage
```

## Les commandes

| Commande | RÃ´le | Modifie le code ? |
|---|---|---|
| `/spec` | Interview + plan dans `specs/projet.md` | âŒ |
| `/adapt` | DÃ©tecte la stack, calibre le comportement | âŒ |
| `/build` | Construit strictement selon le spec | âœ… |
| `/review` | VÃ©rifie, catÃ©gorise les Ã©carts, corrige | âœ… |
| `/checkpoint` | Snapshot de l'Ã©tat dans `specs/progress.md` | âŒ |

## Structure gÃ©nÃ©rÃ©e dans ton projet

```
ton-projet/
â”œâ”€â”€ .claude/
â”‚   â””â”€â”€ commands/
â”‚       â”œâ”€â”€ spec.md
â”‚       â”œâ”€â”€ adapt.md
â”‚       â”œâ”€â”€ build.md
â”‚       â”œâ”€â”€ review.md
â”‚       â””â”€â”€ checkpoint.md
â”œâ”€â”€ specs/
â”‚   â”œâ”€â”€ projet.md        â† source de vÃ©ritÃ© (gÃ©nÃ©rÃ© par /spec)
â”‚   â””â”€â”€ progress.md      â† Ã©tat courant (gÃ©nÃ©rÃ© par /build et /checkpoint)
â””â”€â”€ ... (ton code)
```

## Documentation

- [Guide d'utilisation complet](docs/guide.md)
- [Master prompt d'installation](docs/master-prompt.md)
- [Exemples par stack](docs/exemples-stack.md)

## RÃ¨gles d'or

1. **Ne saute jamais `/spec`** â€” un brief vague = un rÃ©sultat ratÃ©
2. **Lance `/adapt` aprÃ¨s `/spec`** â€” surtout sur des stacks spÃ©cifiques
3. **`specs/projet.md` est sacrÃ©** â€” ne le modifie qu'entre deux cycles
4. **Si `/review` boucle 3 fois** â€” c'est un signal, pas un bug
5. **`/checkpoint` avant toute pause longue**

## CompatibilitÃ©

TestÃ© et pensÃ© pour : Go Â· Python Â· JavaScript/TypeScript Â· Rust  
CI/CD : GitLab CI Â· GitHub Actions  
Projets solo ou en Ã©quipe
