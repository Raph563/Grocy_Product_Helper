# Changelog

## [1.3.1] - 2026-02-20

- Fixed Product Helper settings freeze on `/stocksettings?producthelper=1` by removing persistent overlay mutation-observer loops.
- Overlay visibility on settings pages is now enforced once (no recursive style/class mutation watchers).

## [1.3.0] - 2026-02-20

- Added dedicated settings page rendering for Product Helper on `/stocksettings?producthelper=1` to avoid legacy overlay race conditions.
- Restricted heavy initialization to relevant pages only:
  - settings runtime only on Product Helper settings page.
  - product assistants only on product/form pages.
- Disabled runtime addon state-file probe loops (`*-addon-state.json`) to remove repeated 404 noise and unnecessary network traffic.
- Wrapped addon installed-version refresh in async-safe guarded execution to avoid unhandled startup promise failures.
- Removed global deep DOM observer hot path for settings overlay to reduce mutation overhead and Firefox slowdown/crash risk.

## [1.2.2] - 2026-02-20

- Strengthened settings-overlay anti-hide protection:
  - overlay is forced visible while open, even when external scripts toggle classes/styles.
  - added root DOM observer to restore the overlay if another script removes it from the DOM.
- Improves compatibility with external "hide legacy addon buttons/overlays" toggles.

## [1.2.1] - 2026-02-19

- Fixed shell compose permission handling so `config/data/custom_js.html` stays readable by Grocy runtime even when install/update/uninstall scripts are executed as `root` with restrictive umask.
- Applied to:
  - `addon/scripts/install.sh`
  - `addon/scripts/uninstall.sh`
  - `addon/scripts/update-from-github.sh`
  - `addon/docker-sidecar/entrypoint.sh`

## [1.2.0] - 2026-02-19

- GitHub install/update/uninstall flows now support co-install with `Raph563/Grocy`:
  - this addon writes its own payload file (`config/data/custom_js_product_helper.html`);
  - active Grocy file is composed (`config/data/custom_js.html`) from installed payload sources.
- Docker sidecar now follows the same payload + compose model by default.
- Export scripts now prefer addon-specific payload files before fallback to `custom_js.html`.
- `Raph563/Grocy_Product_Helper` can now be installed independently or together with `Raph563/Grocy` without payload overwrite.

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
