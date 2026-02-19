# Grocy Product Helper - Addon Pack (EN)

Dedicated addon pack for Grocy product helper features.

## Contents

- `dist/custom_js.html`: product-helper frontend payload.
- `scripts/install.*`: local install.
- `scripts/uninstall.*`: rollback.
- `scripts/update-from-github.*`: update from GitHub releases.
- `docker-sidecar/`: Docker sidecar mode.

## Local state

- `config/data/grocy-product-helper-state.json`

## Install

```powershell
cd addon\scripts
.\install.ps1 -GrocyConfigPath "C:\path\to\grocy\config"
```

## Update

```powershell
cd addon\scripts
.\update-from-github.ps1 -GrocyConfigPath "C:\path\to\grocy\config"
```
