# Changelog

## [1.1.0] - 2026-02-19

- Product form: parent mode sync no longer auto-forces userfield parent mode when `no_own_stock` is turned off (non-parent case).
- Barcode robot (product header):
  - advanced OFF/OPF lookup now stops at card suggestion stage;
  - barcode is created only after explicit user selection (click on the suggested card button).
- Product-specific quantity conversion form:
  - added fraction helper input (`1/6`, `2/3`, `6/1`);
  - auto-converts valid fractions to decimal `factor` values before submit;
  - validates fraction input to block invalid save attempts.

## [1.0.0] - 2026-02-19

- Initial standalone release for `Grocy_Product_Helper`.
- Product features split from stats/charts line:
  - OFF/OPF provider tools
  - barcode robot flow
  - photo search/import helpers
  - product helper status terminal
- Added dedicated release asset naming:
  - `grocy-product-helper-addon-vX.Y.Z.zip`
- Added dedicated state file naming:
  - `grocy-product-helper-state.json`
