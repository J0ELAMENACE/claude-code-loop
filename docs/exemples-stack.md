# Exemples par stack

Ce que `/spec` doit capturer dans "Contexte tech" selon ton projet.

---

## Go (ex: API backend)

```
Go 1.24, Gin, MySQL
go-sqlmock, testify
GitLab CI, GOTOOLCHAIN: local
Tests unitaires obligatoires pour chaque handler
Conventions : camelCase pour variables, PascalCase pour exports
```

## Python (ex: API ou script)

```
Python 3.11, FastAPI, SQLAlchemy
pytest, coverage
GitHub Actions
PEP8, type hints obligatoires
```

## JavaScript / TypeScript (ex: frontend ou Node)

```
TypeScript 5, React 18, Vite
Vitest, ESLint, Prettier
GitHub Actions, déploiement Vercel
Conventions : composants en PascalCase, hooks en camelCase
```

## Rust

```
Rust 1.78, Actix-web
cargo test, clippy
GitHub Actions
Conventions : snake_case, Result<> pour toutes les erreurs
```

## Projet fullstack

```
Backend : Go 1.24 / Gin
Frontend : Vanilla JS
Base de données : MySQL
CI/CD : GitLab CI
Tests backend : testify + go-sqlmock
Pas de framework frontend, pas de bundler
```

---

## Ce qui change selon la stack

| Stack | Format de tests | Convention nommage | Structure typique |
|---|---|---|---|
| Go | `func TestXxx(t *testing.T)` | PascalCase exports | `/cmd`, `/internal`, `/pkg` |
| Python | `def test_xxx()` | snake_case | `/src`, `/tests` |
| TypeScript | `describe / it / expect` | camelCase / PascalCase | `/src`, `/components`, `/tests` |
| Rust | `#[test] fn test_xxx()` | snake_case | `/src`, `/tests` |

La loop `/spec → /adapt → /build → /review` est identique pour toutes ces stacks. Seul le contenu du spec change.
