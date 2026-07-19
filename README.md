# compass-one-app-configs

Remote configuration files for metosapps Android apps. Each app reads its
config from `raw.githubusercontent.com` on launch (cached, 6h TTL) — editing a
JSON here changes app behavior **without a store update**.

## Apps

| App | Config | Raw URL |
|---|---|---|
| Compass One (`com.ais.compassone`) | [`compassone/config.json`](compassone/config.json) | `https://raw.githubusercontent.com/metosapps/compass-one-app-configs/main/compassone/config.json` |

## Compass One config keys

- `ads.enabled` / `banner_enabled` / `interstitial_enabled` / `app_open_enabled` — ad toggles
- `ads.interstitial_cooldown_sec`, `interstitial_min_actions`, `ad_free_first_sessions` — frequency caps
- `ads.*_id` — AdMob unit ID overrides (empty = compiled default)
- `iap.sale_mode` + `sale_banner_text` — sale banner on the Pro screen
- `iap.show_remove_ads` — show/hide the Remove Ads product
- `features.qibla_enabled` / `sun_moon_enabled` / `widget_enabled` — feature kill-switches
- `app.force_update` + `min_version_code` + `update_message` — blocking update dialog
- `app.latest_version_code` — informational

Rules: keep keys stable (old app versions ignore unknown keys but need existing
ones); ship risky features OFF and enable here after monitoring.
