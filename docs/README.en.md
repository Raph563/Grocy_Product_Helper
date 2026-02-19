# Grocy Product Helper - EN Guide

## Goal

This repo contains only Grocy product helper features:
- barcode assistant
- OFF/OPF robots
- product photo helpers
- product form helpers

## Install

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

## Update

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

See `addon/docker-sidecar/docker-compose.example.yml`.

## Local state

State file:
- `config/data/grocy-product-helper-state.json`

## Split note

Stats/charts dashboard is maintained in:
- https://github.com/Raph563/Grocy
