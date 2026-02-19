# Grocy Product Helper - Guide FR

## Objectif

Ce repo contient uniquement les fonctions produit Grocy:
- aide code-barres
- robots OFF/OPF
- photo produit
- outils formulaire produit

## Installation

Windows:

```powershell
cd addon\scripts
.\install.ps1 -GrocyConfigPath "C:\path\to\grocy\config"
```

Linux/macOS:

```bash
cd addon/scripts
./install.sh /path/to/grocy/config
```

## Mise a jour

Windows:

```powershell
cd addon\scripts
.\update-from-github.ps1 -GrocyConfigPath "C:\path\to\grocy\config"
```

Linux/macOS:

```bash
cd addon/scripts
./update-from-github.sh --config /path/to/grocy/config
```

## Docker

Voir `addon/docker-sidecar/docker-compose.example.yml`.

## Etat local

Fichier d'etat:
- `config/data/grocy-product-helper-state.json`

## Notes split

Le dashboard stats/graphiques est maintenu dans:
- https://github.com/Raph563/Grocy
